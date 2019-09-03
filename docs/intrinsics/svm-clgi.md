---
title: __svm_clgi
ms.date: 09/02/2019
f1_keywords:
- __svm_clgi
helpviewer_keywords:
- CLGI instruction
- __svm_clgi intrinsic
ms.assetid: 6640f5ab-9472-46f9-a042-e15c4f1ff858
ms.openlocfilehash: 740c76e5dcc8f94b9257272624a6ad3c1f9726c1
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70219962"
---
# <a name="__svm_clgi"></a>__svm_clgi

**Microsoft 'a özgü**

Genel kesme bayrağını temizler.

## <a name="syntax"></a>Sözdizimi

```C
void __svm_clgi( void );
```

## <a name="remarks"></a>Açıklamalar

İşlev, `CLGI` makine yönergesine eşdeğerdir. `__svm_clgi` Genel kesme bayrağı, bir g/ç tamamlama, bir donanım sıcaklık uyarısı veya hata ayıklama özel durumu gibi olaylar nedeniyle mikro işlemcinin kesme, erteleme veya tanıtıcı kesintileri olduğunu belirler.

Bu işlev, bir konağın sanal makine izleyicisinin Konuk işletim sistemiyle ve uygulamalarına yönelik etkileşimini destekler. Daha fazla bilgi için, "AMD64 mimari programcı 'nin El Ile birim 2 ' yi aratın: Sistem programlama, " [AMD Corporation](https://developer.amd.com/resources/developer-guides-manuals/) sitesinde.

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`__svm_clgi`|x86, x64|

**Üst bilgi dosyası** \<Intrin. h >

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)\
[__svm_stgi](../intrinsics/svm-stgi.md)
