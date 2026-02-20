from EmotionDetection import emotion_detector

def test_emotion_detector():

    test_cases = {
        "I am glad this happened": "joy",
        "I am really mad about this": "anger",
        "I feel disgusted just hearing about this": "disgust",
        "I am so sad about this": "sadness",
        "I am really afraid that this will happen": "fear"
    }

    for statement, expected_emotion in test_cases.items():
        result = emotion_detector(statement)
        detected_emotion = result["dominant_emotion"]

        if detected_emotion == expected_emotion:
            print(f"PASSED: '{statement}' → {detected_emotion}")
        else:
            print(f"FAILED: '{statement}' → Expected: {expected_emotion}, Got: {detected_emotion}")

if __name__ == "__main__":
    test_emotion_detector()
