---
UID: NC:acxelements.EVT_ACX_STREAMAUDIOENGINE_RETRIEVE_PRESENTATION_POSITION
tech.root: audio 
title: EVT_ACX_STREAMAUDIOENGINE_RETRIEVE_PRESENTATION_POSITION
ms.date: 04/29/2022
targetos: Windows
description: The EVT_ACX_STREAMAUDIOENGINE_RETRIEVE_PRESENTATION_POSITION callback function is implemented by the driver and is called to retrieve the current position within the audio data being rended to the stream audio engine node.
prerelease: true
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxelements.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - acxelements.h
api_name:
 - EVT_ACX_STREAMAUDIOENGINE_RETRIEVE_PRESENTATION_POSITION
f1_keywords:
 - EVT_ACX_STREAMAUDIOENGINE_RETRIEVE_PRESENTATION_POSITION
 - acxelements/EVT_ACX_STREAMAUDIOENGINE_RETRIEVE_PRESENTATION_POSITION
dev_langs:
 - c++
---

## -description

The **EVT_ACX_STREAMAUDIOENGINE_RETRIEVE_PRESENTATION_POSITION** callback function is implemented by the driver and is called to retrieve the current position within the audio data being rended to the stream audio engine node.

## -parameters

### -param StreamAudioEngine

An existing, initialized, ACXSTREAMAUDIOENGINE object. For more information about ACX objects, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

### -param PositionInBlocks

Specifies the block offset from the start of the stream to the current post-decoded, uncompressed position in the stream. See [KSAUDIO_PRESENTATION_POSITION structure](/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-ksaudio_presentation_position) for more information on this value. 

### -param QPCPosition

Specifies the value of the performance counter at the time that the audio driver reads the presentation position in response to the callback.  See [KSAUDIO_PRESENTATION_POSITION structure](/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-ksaudio_presentation_position) for more information on this value. 

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

### Example

Example usage is shown below.

```cpp
EVT_ACX_STREAMAUDIOENGINE_RETRIEVE_PRESENTATION_POSITION    CodecR_EvtAcxStreamAudioEngineRetrievePresentationPosition;

NTSTATUS
CodecR_EvtAcxStreamAudioEngineRetrievePresentationPosition(
    _In_    ACXSTREAMAUDIOENGINE    StreamAudioEngine,
    _Out_   PULONGLONG              PositionInBlocks,
    _Out_   PULONGLONG              QPCPosition
)
{
    NTSTATUS status = STATUS_INVALID_PARAMETER;
    ACXSTREAM stream;
    PCODEC_STREAM_CONTEXT ctx;
    CRenderStreamEngine * streamEngine = NULL;

    PAGED_CODE();

    stream = AcxStreamAudioEngineGetStream(StreamAudioEngine);
    if (stream)
    {
        ctx = GetCodecStreamContext(stream);

        streamEngine = static_cast<CRenderStreamEngine*>(ctx->StreamEngine);

        status = streamEngine->GetPresentationPosition(PositionInBlocks, QPCPosition);
    }

    return status;
}
```

## -see-also

- [acxelements.h header](index.md)