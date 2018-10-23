---
title: PROTO | Microsoft Docs
ms.custom: ''
ms.date: 10/22/2018
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- PROTO
dev_langs:
- C++
helpviewer_keywords:
- PROTO directive
ms.assetid: 0487ee16-9dc7-43d1-9445-cd1601f5a080
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4fd00263f3b4a7ffcf23ccd0501989c0d40c637d
ms.sourcegitcommit: f3a5dc788e62bb36e2d9bc3e62e0aa533422408b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49644069"
---
# <a name="proto"></a>PROTO

Bir işlev veya yordam prototipleri. İşlev prototipli PROTO yönergesi tarafından kullanarak çağırabilirsiniz [INVOKE](invoke.md) yönergesi.

## <a name="syntax"></a>Sözdizimi

> *Etiket* **PROTO** \[ *uzaklık*] \[ *langtype*] \[ __,__ \[ *parametre*]__:__*etiketi*]...

### <a name="parameters"></a>Parametreler

*Etiket*<br/>
Prototipli işlev adı.

*uzaklık*<br/>
(İsteğe bağlı) 16-bit bellek modellerinde Varsayılanı geçersiz kılmak ve belirtmek için kullanılan **yakın** veya **uzak** çağırır.

*langtype*<br/>
(İsteğe bağlı) Yordamlar ve ortak semboller için arama ve adlandırma kuralı ayarlar. Desteklenen kuralları şunlardır:

- 32-bit **DÜZ** modeli: **C**, **STDCALL**

- 16-bit modelleri: **C**, **temel**, **FORTRAN**, **PASCAL**, **SYSCALL**, **STDCALL**

*Parametre*<br/>
Bir işlev parametresi için isteğe bağlı adı.

*Etiket*<br/>
İşlevi parametrenin türü.

*Parametre* ve *etiketi* parametreleri görünebilir birden çok kez kez için geçirilen her bağımsız değişken.

## <a name="example"></a>Örnek

Bu örnek, gösterir bir **PROTO** adlı bir işlev bildirimi `addup3` kullanan bir **yakın** 16-bit modeli varsayılan yordam çağrılarını ve kullandığı için geçersiz kılmak için çağrı **C**çağırma parametreleri için yığın ve dönüş değerleri. İki bağımsız değişkeni alır bir **WORD** ve **VARARG**.

```MASM
addup3 PROTO NEAR C, argcount:WORD, arg1:VARARG
```

## <a name="see-also"></a>Ayrıca bkz.

[Yönergeler Başvurusu](directives-reference.md)<br/>
[. Modeli Başvurusu](dot-model.md)<br/>
