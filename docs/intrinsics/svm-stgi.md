---
description: 'Hakkında daha fazla bilgi edinin: __svm_stgi'
title: __svm_stgi
ms.date: 09/02/2019
f1_keywords:
- __svm_stgi
helpviewer_keywords:
- __svm_stgi intrinsic
- STGI instruction
ms.assetid: 96488da4-5587-4e99-8674-627a9e51be84
ms.openlocfilehash: 8a6c7c221ed0bbf71a00685e8a0545818dd507a1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336852"
---
# <a name="__svm_stgi"></a>__svm_stgi

**Microsoft'a Özgü**

Genel kesme bayrağını ayarlar.

## <a name="syntax"></a>Syntax

```C
void __svm_stgi(void);
```

## <a name="remarks"></a>Açıklamalar

`__svm_stgi`İşlev, `STGI` makine yönergesine eşdeğerdir. Genel kesme bayrağı, bir g/ç tamamlama, bir donanım sıcaklık uyarısı veya hata ayıklama özel durumu gibi olaylar nedeniyle mikro işlemcinin kesme, erteleme veya tanıtıcı kesintileri olduğunu belirler.

Bu işlev, bir konağın sanal makine izleyicisinin Konuk işletim sistemiyle ve uygulamalarına yönelik etkileşimini destekler. Daha fazla bilgi için, [AMD Corporation](https://developer.amd.com/resources/developer-guides-manuals/) SITESINDE "AMD64 Architecture Programmer 'ın el ile Volume 2: sistem programlama" ifadesini aratın.

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`__svm_stgi`|x86, x64|

**Üst bilgi dosyası**\<intrin.h>

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)\
[__svm_clgi](../intrinsics/svm-clgi.md)
