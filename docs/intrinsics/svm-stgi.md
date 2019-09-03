---
title: __svm_stgi
ms.date: 09/02/2019
f1_keywords:
- __svm_stgi
helpviewer_keywords:
- __svm_stgi intrinsic
- STGI instruction
ms.assetid: 96488da4-5587-4e99-8674-627a9e51be84
ms.openlocfilehash: 6bd731951b440d3d2597d54c9a52d9f8640a5c5f
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70219839"
---
# <a name="__svm_stgi"></a>__svm_stgi

**Microsoft 'a özgü**

Genel kesme bayrağını ayarlar.

## <a name="syntax"></a>Sözdizimi

```C
void __svm_stgi(void);
```

## <a name="remarks"></a>Açıklamalar

İşlev, `STGI` makine yönergesine eşdeğerdir. `__svm_stgi` Genel kesme bayrağı, bir g/ç tamamlama, bir donanım sıcaklık uyarısı veya hata ayıklama özel durumu gibi olaylar nedeniyle mikro işlemcinin kesme, erteleme veya tanıtıcı kesintileri olduğunu belirler.

Bu işlev, bir konağın sanal makine izleyicisinin Konuk işletim sistemiyle ve uygulamalarına yönelik etkileşimini destekler. Daha fazla bilgi için, "AMD64 mimari programcı 'nin El Ile birim 2 ' yi aratın: Sistem programlama, " [AMD Corporation](https://developer.amd.com/resources/developer-guides-manuals/) sitesinde.

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`__svm_stgi`|x86, x64|

**Üst bilgi dosyası** \<Intrin. h >

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)\
[__svm_clgi](../intrinsics/svm-clgi.md)
