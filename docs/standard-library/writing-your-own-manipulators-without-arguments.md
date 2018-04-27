---
title: Bağımsız değişkenler olmadan kendi Manipülatörlerinizi yazma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- manipulators
ms.assetid: 2dc62d09-45b7-454d-bd9d-55f3c72c206d
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7661e8df55f8b7de0cac546c15369247cc6bf2c8
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="writing-your-own-manipulators-without-arguments"></a>Bağımsız Değişkenler Olmadan Kendi Manipülatörlerinizi Yazma

Bağımsız değişkenler kullanmayın manipülatörlerinizi yazma sınıf türetme ne karmaşık makroları kullanımını gerektirir. Yazıcı çifti gerektirir varsayalım \<ESC > [Kalın modu girmek için tıklatın. Akışa doğrudan bu çifti ekleyebilirsiniz:

```cpp
cout <<"regular " <<'\033' <<'[' <<"boldface" <<endl;
```

Veya tanımlayabilirsiniz `bold` karakterleri ekler manipulator:

```cpp
ostream& bold(ostream& os) {
    return os <<'\033' <<'[';
}
cout <<"regular " <<bold <<"boldface" <<endl;
```

Genel olarak tanımlanan `bold` işlev sürer bir `ostream` başvuru bağımsız değişkeni ve döndürür `ostream` başvuru. Tüm özel sınıfı öğelere erişim gerekmediği için üye işlevi veya bir arkadaş değil. `bold` İşlevi bağlayan akışa çünkü akışın `<<` işleci aşırı yüklenmiş işlevi, bu tür kabul etmek için şuna benzer bir bildirimi kullanarak:

```cpp
_Myt& operator<<(ios_base& (__cdecl *_Pfn)(ios_base&))
{     // call ios_base manipulator
 (*_Pfn)(*(ios_base *)this);

    return (*this);

}
```

Diğer aşırı yüklenmiş işleçler genişletmek için bu özelliği kullanın. Bu durumda, arızi olduğundan, `bold` akışa karakter ekler. Bitişik karakter yazdırıldığında bu akışa mutlaka eklendiğinde, işlev çağrılır. Bu nedenle, yazdırma akışın arabelleğe alma nedeniyle Gecikmeli.

## <a name="see-also"></a>Ayrıca bkz.

[Çıkış Akışları](../standard-library/output-streams.md)<br/>
