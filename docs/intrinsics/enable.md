---
title: _enable
ms.date: 11/04/2016
f1_keywords:
- _enable
- _enable_cpp
helpviewer_keywords:
- enable intrinsic
- _enable intrinsic
- ssm instruction
ms.assetid: 8bee669b-6bd8-4e25-9383-bb7d57295b4d
ms.openlocfilehash: e1ece6d6f4040b81b55d8400407d46f165b56b53
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59024523"
---
# <a name="enable"></a>_enable

**Microsoft'a Özgü**

Kesme sağlar.

## <a name="syntax"></a>Sözdizimi

```
void _enable(void);
```

## <a name="requirements"></a>Gereksinimler

|İç|Mimari|
|---------------|------------------|
|`_enable`|x86, ARM, x64|

**Üst bilgi dosyası** \<intrin.h >

## <a name="remarks"></a>Açıklamalar

`_enable` İşlemci Kesme bayrağı bildirir. X86 sistemleri, bu işlev Kesme bayrağı ayarlanmış oluşturur (`sti`) yönerge.

Bu işlev, yalnızca çekirdek modunda kullanılabilir. Kullanıcı modunda kullandıysanız, bir ayrıcalıklı yönerge özel durum oluşturulur.

**END Microsoft'a Özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)