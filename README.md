import pymorphy2

morph = pymorphy2.MorphAnalyzer()
n = input()
word = morph.parse(n)[0]
if 'NOUN' in word.tag:
    print(f'''Единственное число:
Именительный падеж: {word.inflect({'NOUN', 'nomn'}).word}
Родительный падеж: {word.inflect({'NOUN', 'gent'}).word}
Дательный падеж: {word.inflect({'NOUN', 'datv'}).word}
Винительный падеж: {word.inflect({'NOUN', 'accs'}).word}
Творительный падеж: {word.inflect({'NOUN', 'ablt'}).word}
Предложный падеж: {word.inflect({'NOUN', 'loct'}).word}
Множественное число:
Именительный падеж: {word.inflect({'NOUN', 'nomn', 'plur'}).word}
Родительный падеж: {word.inflect({'NOUN', 'gent', 'plur'}).word}
Дательный падеж: {word.inflect({'NOUN', 'datv', 'plur'}).word}
Винительный падеж: {word.inflect({'NOUN', 'accs', 'plur'}).word}
Творительный падеж: {word.inflect({'NOUN', 'ablt', 'plur'}).word}
Предложный падеж: {word.inflect({'NOUN', 'loct', 'plur'}).word}''')
else:
    print('Не существительное')
