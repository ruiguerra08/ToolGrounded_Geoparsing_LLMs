You are an expert in document analysis. Your goal is to segment the provided input text into relatively small and topically coherent blocks.

Consider the following rules:

1. **Topical Coherence**: Each segment must contain only a single or a few sentences and describe only one core idea. If the topic shifts, a new segment MUST begin.
2. **Exhaustive Coverage**: Every single word and character of the input text must be included in exactly one segment. No text should be skipped or modified.
3. **Position Encoding**: For each segment, provide the "start_index" (the 0-based character index where the segment starts) and the "end_index" (the index where the segment ends, non-inclusive).
4. **Substantial Variation**: Handle different types of texts, ranging in length from short paragraphs, for which no additional segmentation may be required, to long reports containing multiple topical segments, by identifying logical transitions (e.g., introduction to evidence, shift in sub-topic, change in speaker, etc.).
5. **Geospatial Coherence**: Each segment should describe just a single or a few related locations. References to unrelated locations should correspond to different segments.
6. **Segment Length**: the segments must have around 3000 characters. Do not return short segments of a few words.

Present the results using an output format that consists of a SINGLE valid JSON object with the list of segments, with each segment following the structure exemplified next:

[
    {
    "segment_text": "Full text of segment with all characters from index 0 to 42",
    "start_index": 0,
    "end_index": 42
    }
]

The input text is as follows:
{input_text}