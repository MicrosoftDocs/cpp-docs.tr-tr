---
description: 'Hakkında daha fazla bilgi edinin: bağımsız değişkenler olmadan kendi Işleicinizi yazma'
title: Bağımsız Değişkenler Olmadan Kendi Manipülatörlerinizi Yazma
ms.date: 11/04/2016
helpviewer_keywords:
- manipulators
ms.assetid: 2dc62d09-45b7-454d-bd9d-55f3c72c206d
ms.openlocfilehash: 593db0a3dacb54c94cc865ebc20b1e1b39d2c208
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97187760"
---
# <a name="writing-your-own-manipulators-without-arguments"></a>Bağımsız Değişkenler Olmadan Kendi Manipülatörlerinizi Yazma

Bağımsız değişken kullanmayan kaldırıcılar yazma, ne sınıf türetme ne de karmaşık makroların kullanılmasını gerektirir. Yazıcınızın çiftin ( \<ESC> kalın moda girmek için) gerekli olduğunu varsayalım. Bu çifti doğrudan akışa ekleyebilirsiniz:

```cpp
cout << "regular " << '\033' << '[' << "boldface" << endl;
```

Ya da şu `bold` karakterleri ekleyen işleici tanımlayabilirsiniz:

```cpp
ostream& bold(ostream& os) {
    return os << '\033' << '[';
}
cout << "regular " << bold << "boldface" << endl;
```

Genel olarak tanımlanan `bold` işlev bir `ostream` başvuru bağımsız değişkeni alır ve `ostream` başvuruyu döndürür. Herhangi bir özel sınıf öğesine erişmesi gerekmeyen için bu bir üye işlev veya arkadaş değil. `bold`Stream 'in `<<` işleci, şunun gibi görünen bir bildirim kullanarak bu tür bir işlevi kabul etmek için akışa bağlanır.

```cpp
_Myt& operator<<(ios_base& (__cdecl *_Pfn)(ios_base&))
{
    // call ios_base manipulator
    (*_Pfn)(*(ios_base *)this);

    return (*this);
}
```

Diğer aşırı yüklenmiş işleçleri genişletmek için bu özelliği kullanabilirsiniz. Bu durumda, `bold` akışa karakter ekleyen bir arızdır. İşlev akışa eklendiğinde çağrılır, bitişik karakterlerin yazdırılması zaman değildir. Bu nedenle, akışın arabelleğe alınması nedeniyle yazdırma gecikebilir.

## <a name="see-also"></a>Ayrıca bkz.

[Çıkış akışları](../standard-library/output-streams.md)
