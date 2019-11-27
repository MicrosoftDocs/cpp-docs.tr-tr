---
title: PROTO
ms.date: 10/22/2018
f1_keywords:
- PROTO
helpviewer_keywords:
- PROTO directive
ms.assetid: 0487ee16-9dc7-43d1-9445-cd1601f5a080
ms.openlocfilehash: 24ec2a9abc6c8b76fc81f6d412019296c53160f4
ms.sourcegitcommit: 9ee5df398bfd30a42739632de3e165874cb675c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74394751"
---
# <a name="proto"></a>PROTO

Prototiplerde bir işlev veya yordam. [Invoke](invoke.md) YÖNERGESINI kullanarak Prot yönergesini kullanarak prototip işlevini çağırabilirsiniz.

## <a name="syntax"></a>Sözdizimi

> *etiket* **proto** ⟦*uzaklık*⟧ ⟦*dil türü*⟧ ⟦ __,__ ⟦*parametre*⟧ __:__ *Tag* ... ⟧

### <a name="parameters"></a>Parametreler

*etiket*\
Prototipte belirlenmiş işlevin adı.

*uzaklık*\
Seçim Varsayılan değer geçersiz kılmak ve **yakın** veya **uzak** çağrıların göstermek için 16 bit bellek modellerinde kullanılır.

*dil türü*\
Seçim Yordamlar ve genel semboller için çağrı ve adlandırma kuralını ayarlar. Desteklenen kurallar şunlardır:

- 32-bit **düz** model: **C**, **stdcall**

- 16 bit modeller: **C**, **temel**, **FORTRAN**, **Pascal**, **syscall**, **stdcall**

*parametre*\
Bir işlev parametresi için isteğe bağlı ad.

*etiket*\
Bir işlev parametresinin türü.

*Parametre* ve *etiket* parametreleri, her geçilen bağımsız değişken için bir kez olmak üzere birden çok kez bulunabilir.

## <a name="example"></a>Örnek

Bu örnek, yordam çağrıları için 16 bit model varsayılanını geçersiz kılmak üzere **yakın** bir çağrı kullanan `addup3` adlı bir Işlev için **proto** bildirimini gösterir ve yığın parametreleri ve dönüş değerleri için **C** çağırma kuralını kullanır. İki bağımsız değişkeni, bir **sözcük** ve bir **vararg**alır.

```MASM
addup3 PROTO NEAR C, argcount:WORD, arg1:VARARG
```

## <a name="see-also"></a>Ayrıca bkz.

[Yönergeler başvurusu](directives-reference.md)\
[. MODEL başvurusu](dot-model.md)
