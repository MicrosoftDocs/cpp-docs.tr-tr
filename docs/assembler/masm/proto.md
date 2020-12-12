---
description: 'Hakkında daha fazla bilgi edinin: PROTO'
title: PROTO
ms.date: 12/06/2019
f1_keywords:
- PROTO
helpviewer_keywords:
- PROTO directive
ms.assetid: 0487ee16-9dc7-43d1-9445-cd1601f5a080
ms.openlocfilehash: 34dbf9d877dbbc52484e45c5f94212108aeacb42
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97126015"
---
# <a name="proto"></a>PROTO

Prototiplerde bir işlev veya yordam. [Invoke](invoke.md) YÖNERGESINI kullanarak Prot yönergesini kullanarak prototip işlevini çağırabilirsiniz.

## <a name="syntax"></a>Syntax

> *etiket* **proto** ⟦*uzaklık*⟧ ⟦*dil türü*⟧ ⟦__,__ ⟦*parametre*⟧__:__*Tag* ... ⟧

### <a name="parameters"></a>Parametreler

*etiketin*\
Prototipte belirlenmiş işlevin adı.

*uzaklık* (yalnızca 32-BIT masa.) \
Seçim Varsayılan değer geçersiz kılmak ve **yakın** veya **uzak** çağrıların göstermek için 16 bit bellek modellerinde kullanılır.

*dil türü* (yalnızca 32-BIT masa.) \
Seçim Yordamlar ve genel semboller için çağrı ve adlandırma kuralını ayarlar. Desteklenen kurallar şunlardır:

- 32-bit **düz** model: **C**, **stdcall**

- 16 bit modeller: **C**, **temel**, **FORTRAN**, **Pascal**, **syscall**, **stdcall**

*parametresinin*\
Bir işlev parametresi için isteğe bağlı ad.

*Etiket*\
Bir işlev parametresinin türü.

*Parametre* ve *etiket* parametreleri, her geçilen bağımsız değişken için bir kez olmak üzere birden çok kez bulunabilir.

## <a name="example"></a>Örnek

Bu örnek  `addup3` , yordam çağrıları için 16 bit model varsayılanını geçersiz kılmak üzere **yakın** bir çağrı kullanan adlı bir işlev için proto bildirimini gösterir ve yığın parametreleri ve dönüş değerleri için **C** çağırma kuralını kullanır. İki bağımsız değişkeni, bir **sözcük** ve bir **vararg** alır.

```MASM
addup3 PROTO NEAR C, argcount:WORD, arg1:VARARG
```

## <a name="see-also"></a>Ayrıca bkz.

[Yönergeler başvurusu](directives-reference.md)\
[. MODEL başvurusu](dot-model.md)\
[MASMG BNF dilbilgisi](masm-bnf-grammar.md)
