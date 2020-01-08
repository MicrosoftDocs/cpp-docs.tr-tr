---
title: PROTO
ms.date: 12/06/2019
f1_keywords:
- PROTO
helpviewer_keywords:
- PROTO directive
ms.assetid: 0487ee16-9dc7-43d1-9445-cd1601f5a080
ms.openlocfilehash: 3963fa29050653d1706222d33734c4b5f2a17919
ms.sourcegitcommit: 0781c69b22797c41630601a176b9ea541be4f2a3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/20/2019
ms.locfileid: "75318650"
---
# <a name="proto"></a>PROTO

Prototiplerde bir işlev veya yordam. [Invoke](invoke.md) YÖNERGESINI kullanarak Prot yönergesini kullanarak prototip işlevini çağırabilirsiniz.

## <a name="syntax"></a>Sözdizimi

> *etiket* **proto** ⟦*uzaklık*⟧ ⟦*dil türü*⟧ ⟦ __,__ ⟦*parametre*⟧ __:__ *Tag* ... ⟧

### <a name="parameters"></a>Parametreler

*etiket*\
Prototipte belirlenmiş işlevin adı.

*uzaklık* (yalnızca 32-BIT masa.) \
Seçim Varsayılan değer geçersiz kılmak ve **yakın** veya **uzak** çağrıların göstermek için 16 bit bellek modellerinde kullanılır.

*dil türü* (yalnızca 32-BIT masa.) \
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
[. MODEL başvurusu](dot-model.md)\
[MASMG BNF dilbilgisi](masm-bnf-grammar.md)
