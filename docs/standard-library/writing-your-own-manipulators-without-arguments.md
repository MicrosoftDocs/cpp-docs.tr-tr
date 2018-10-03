---
title: Bağımsız değişkenler olmadan kendi Manipülatörlerinizi yazma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- manipulators
ms.assetid: 2dc62d09-45b7-454d-bd9d-55f3c72c206d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e8bfad1919863a58554604fe6d32b4563e57a14a
ms.sourcegitcommit: 1d9bd38cacbc783fccd3884b7b92062161c91c84
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/03/2018
ms.locfileid: "48235717"
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
