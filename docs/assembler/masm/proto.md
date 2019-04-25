---
title: PROTO
ms.date: 10/22/2018
f1_keywords:
- PROTO
helpviewer_keywords:
- PROTO directive
ms.assetid: 0487ee16-9dc7-43d1-9445-cd1601f5a080
ms.openlocfilehash: 616b6be2a5c191ebc67d61288cb5fa6c183091fa
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62210527"
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

- 16-bit modelleri: **C**, **BASIC**, **FORTRAN**, **PASCAL**, **SYSCALL**, **STDCALL**

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
