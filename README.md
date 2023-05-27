largest = None
smallest = None
while True:
    weight = input('Enter weight: ')
    if weight == 'done':
        break

    try:
        weight = int(weight)
    except ValueError:
        print('Invalid input. ')
        continue

    unit = input('(K)gs? or (L)bs?: ')

    if unit.upper() == 'K':
        converted = weight / 2.2
        print(f'Your weight in Lbs: {converted:.2f}')
    elif unit.upper() == 'L':
        converted = float(weight) * 2.2
        print(f'Your weight in Kgs: {converted:.2f}')
    else:
        print('Invalid input: ')
        continue
    if largest is None or largest < converted:
        largest = converted
    if smallest is None or smallest > converted:
        smallest = converted

print(f'all done, Here are your largest '
      f'and smallest results: {int(largest)} , {int(smallest)}')
