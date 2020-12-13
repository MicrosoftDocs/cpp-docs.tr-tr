---
description: 'Hakkında daha fazla bilgi edinin: __svm_clgi'
title: __svm_clgi
ms.date: 09/02/2019
f1_keywords:
- __svm_clgi
helpviewer_keywords:
- CLGI instruction
- __svm_clgi intrinsic
ms.assetid: 6640f5ab-9472-46f9-a042-e15c4f1ff858
ms.openlocfilehash: d0b372e28b0b119d3576dd87b34f1edf883f1337
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336868"
---
# <a name="__svm_clgi"></a>__svm_clgi

**Microsoft'a Özgü**

Genel kesme bayrağını temizler.

## <a name="syntax"></a>Syntax

```C
void __svm_clgi( void );
```

## <a name="remarks"></a>Açıklamalar

`__svm_clgi`İşlev, `CLGI` makine yönergesine eşdeğerdir. Genel kesme bayrağı, bir g/ç tamamlama, bir donanım sıcaklık uyarısı veya hata ayıklama özel durumu gibi olaylar nedeniyle mikro işlemcinin kesme, erteleme veya tanıtıcı kesintileri olduğunu belirler.

Bu işlev, bir konağın sanal makine izleyicisinin Konuk işletim sistemiyle ve uygulamalarına yönelik etkileşimini destekler. Daha fazla bilgi için, [AMD Corporation](https://developer.amd.com/resources/developer-guides-manuals/) SITESINDE "AMD64 Architecture Programmer 'ın el ile Volume 2: sistem programlama" ifadesini aratın.

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`__svm_clgi`|x86, x64|

**Üst bilgi dosyası**\<intrin.h>

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)\
[__svm_stgi](../intrinsics/svm-stgi.md)
