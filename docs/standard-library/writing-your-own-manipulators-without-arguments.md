---
title: Bağımsız Değişkenler Olmadan Kendi Manipülatörlerinizi Yazma
ms.date: 11/04/2016
helpviewer_keywords:
- manipulators
ms.assetid: 2dc62d09-45b7-454d-bd9d-55f3c72c206d
ms.openlocfilehash: 0c3037c007e9388485f9553f9d2b0a69a1980b9a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50428415"
---
# <a name="writing-your-own-manipulators-without-arguments"></a>Bağımsız Değişkenler Olmadan Kendi Manipülatörlerinizi Yazma

Bağımsız değişkenler kullanmayan manipülatörlerinizi yazma sınıf türetme ne karmaşık makroların kullanılması gerekir. Yazıcı çifti gerektirir varsayalım \<ESC > [Kalın moduna girmek için. Akışa doğrudan bu çifti ekleyebilirsiniz:

```cpp
cout << "regular " << '\033' << '[' << "boldface" << endl;
```

Veya tanımlayabilirsiniz `bold` karakterleri ekleyen işleyici:

```cpp
ostream& bold(ostream& os) {
    return os << '\033' << '[';
}
cout << "regular " << bold << "boldface" << endl;
```

Genel olarak tanımlanan `bold` işlevini alır bir `ostream` başvuru bağımsız değişkeni ve döndürür `ostream` başvuru. Herhangi bir özel sınıf öğelere erişim gerekmediği için bir arkadaş veya bir üye işlev değil. `bold` İşlevi, çünkü akışa bağlar akışın `<<` işleci aşırı yüklenmiş işlev türü kabul etmek için şuna benzer bir bildirimi kullanarak:

```cpp
_Myt& operator<<(ios_base& (__cdecl *_Pfn)(ios_base&))
{
    // call ios_base manipulator
    (*_Pfn)(*(ios_base *)this);

    return (*this);
}
```

Bu özellik, diğer aşırı yüklenmiş işleçler genişletmek için kullanabilirsiniz. Bu durumda, arızi olduğu, `bold` karakter akışı halinde ekler. Bitişik karakter yazdırıldığında akışa mutlaka eklendiği işlevi çağrılır. Bu nedenle, yazdırma akışın arabelleğe alma nedeniyle Gecikmeli.

## <a name="see-also"></a>Ayrıca bkz.

[Çıkış Akışları](../standard-library/output-streams.md)<br/>
