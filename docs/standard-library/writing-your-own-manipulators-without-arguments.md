---
title: Bağımsız Değişkenler Olmadan Kendi Manipülatörlerinizi Yazma
ms.date: 11/04/2016
helpviewer_keywords:
- manipulators
ms.assetid: 2dc62d09-45b7-454d-bd9d-55f3c72c206d
ms.openlocfilehash: 9a1f72ae3e6860d8ab532a72a1776b77c7204f48
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68450910"
---
# <a name="writing-your-own-manipulators-without-arguments"></a>Bağımsız Değişkenler Olmadan Kendi Manipülatörlerinizi Yazma

Bağımsız değişken kullanmayan kaldırıcılar yazma, ne sınıf türetme ne de karmaşık makroların kullanılmasını gerektirir. Yazıcınızda \<ESC tuşuna > [kalın moduna girmek için ESC) gerekli olduğunu varsayalım. Bu çifti doğrudan akışa ekleyebilirsiniz:

```cpp
cout << "regular " << '\033' << '[' << "boldface" << endl;
```

Ya da şu karakterleri ekleyen `bold` işleici tanımlayabilirsiniz:

```cpp
ostream& bold(ostream& os) {
    return os << '\033' << '[';
}
cout << "regular " << bold << "boldface" << endl;
```

Genel olarak tanımlanan `bold` işlev bir `ostream` `ostream` başvuru bağımsız değişkeni alır ve başvuruyu döndürür. Herhangi bir özel sınıf öğesine erişmesi gerekmeyen için bu bir üye işlev veya arkadaş değil. `bold` Stream 'in`<<` işleci, şunun gibi görünen bir bildirim kullanarak bu tür bir işlevi kabul etmek için akışa bağlanır.

```cpp
_Myt& operator<<(ios_base& (__cdecl *_Pfn)(ios_base&))
{
    // call ios_base manipulator
    (*_Pfn)(*(ios_base *)this);

    return (*this);
}
```

Diğer aşırı yüklenmiş işleçleri genişletmek için bu özelliği kullanabilirsiniz. Bu durumda, akışa karakter ekleyen bir `bold` arızdır. İşlev akışa eklendiğinde çağrılır, bitişik karakterlerin yazdırılması zaman değildir. Bu nedenle, akışın arabelleğe alınması nedeniyle yazdırma gecikebilir.

## <a name="see-also"></a>Ayrıca bkz.

[Çıkış Akışları](../standard-library/output-streams.md)
