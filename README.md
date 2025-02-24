def text_to_emoji(sentence):
    emoji_dict = {
        "love": "❤",
        "pizza": "🍕",
        "cats": "🐱",
        "dog": "🐶",
        "happy": "😊",
        "sad": "😢",
        "laugh": "😂",
        "angry": "😠",
        "sun": "☀️",
        "moon": "🌙"
    }

    words = sentence.split()
    converted_words = []

    for word in words:
        stripped_word = ''.join(char for char in word if char.isalnum())
        if stripped_word.lower() in emoji_dict:
            converted_words.append(emoji_dict[stripped_word.lower()])
        else:
            converted_words.append(word)

    return ' '.join(converted_words)

if __name__ == "__main__":
    sentence = input("Enter a sentence: ")
    result = text_to_emoji(sentence)
    print(result)
