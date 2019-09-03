---
title: _enable
ms.date: 09/02/2019
f1_keywords:
- _enable
- _enable_cpp
helpviewer_keywords:
- enable intrinsic
- _enable intrinsic
- ssm instruction
ms.assetid: 8bee669b-6bd8-4e25-9383-bb7d57295b4d
ms.openlocfilehash: 7adcd4eac807b8d0937efbbe6d89f8ad6dcb157c
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70217877"
---
# <a name="_enable"></a>_enable

**Microsoft 'a özgü**

Kesmeleri izin vermez.

## <a name="syntax"></a>Sözdizimi

```C
void _enable(void);
```

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`_enable`|x86, ARM, x64, ARM64|

**Üst bilgi dosyası** \<Intrin. h >

## <a name="remarks"></a>Açıklamalar

`_enable`İşlemciyi kesme bayrağını ayarlamaya yöneltir. X86 sistemlerinde, bu işlev kesme bayrağını ayarla (`sti`) yönergesini üretir.

Bu işlev yalnızca çekirdek modunda kullanılabilir. Kullanıcı modunda kullanılıyorsa, ayrıcalıklı yönerge özel durumu oluşturulur.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)
