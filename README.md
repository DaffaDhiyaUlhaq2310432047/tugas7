def konversi_suhu(suhu, satuan):
    if satuan == 'C':
        if suhu < -273.15:
            return "Suhu yang Anda inputkan tidak valid!"
        fahrenheit = (suhu * 9/5) + 32
        reamur = suhu * 4/5
        kelvin = suhu + 273.15
        return suhu, fahrenheit, reamur, kelvin
    elif satuan == 'F':
        if suhu < -459.67:
            return "Suhu yang Anda inputkan tidak valid!"
        celcius = (suhu - 32) * 5/9
        reamur = (celcius) * 4/5
        kelvin = celcius + 273.15
        return celcius, suhu, reamur, kelvin
    elif satuan == 'R':
        if suhu < -218.52:
            return "Suhu yang Anda inputkan tidak valid!"
        celcius = suhu * 5/4
        fahrenheit = (celcius * 9/5) + 32
        kelvin = celcius + 273.15
        return celcius, fahrenheit, suhu, kelvin
    elif satuan == 'K':
        if suhu < 0:
            return "Suhu yang Anda inputkan tidak valid!"
        celcius = suhu - 273.15
        fahrenheit = (celcius * 9/5) + 32
        reamur = celcius * 4/5
        return celcius, fahrenheit, reamur, suhu
    else:
        return "Satuan suhu tidak valid!"

    
suhu_input = float(input("Masukkan suhu: "))
satuan_input = input("Masukkan satuan suhu (C/F/R/K): ")

print ("Konversi suhu",(suhu_input,satuan_input))

hasil_konversi = konversi_suhu(suhu_input, satuan_input)


if isinstance(hasil_konversi, tuple):
    print("|| Satuan suhu || Derajat suhu ||")
    print("||-------------||--------------||")
    print("|| Reamur      ||", "{:<12.2f} ||".format(hasil_konversi[2]))
    print("|| Fahrenheit  ||", "{:<12.2f} ||".format(hasil_konversi[1]))
    print("|| Kelvin      ||", "{:<12.2f} ||".format(hasil_konversi[3]))
    print("|| Celcius     ||", "{:<12.2f} ||".format(hasil_konversi[0]))
else:
    print(hasil_konversi)
