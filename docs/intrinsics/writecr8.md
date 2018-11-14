---
title: __writecr8
ms.date: 11/04/2016
f1_keywords:
- _writecr8
helpviewer_keywords:
- _writecr8 intrinsic
ms.assetid: 6f8bd632-dddb-4335-971e-1acee24aa2b9
ms.openlocfilehash: 1a7b31ed7e370c4dd3fee9e5a205be6e34ba560b
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/09/2018
ms.locfileid: "51325790"
---
# <a name="writecr8"></a>__writecr8

**Microsoft'a özgü**

Değeri Yazar `Data` CR8 kaydı.

## <a name="syntax"></a>Sözdizimi

```
void writecr8(
   unsigned __int64 Data
);
```

#### <a name="parameters"></a>Parametreler

*Veri*<br/>
[in] CR8 kasaya yazılacak değer.

## <a name="requirements"></a>Gereksinimler

|İç|Mimari|
|---------------|------------------|
|`__writecr8`|X64|

**Üst bilgi dosyası** \<intrin.h >

## <a name="remarks"></a>Açıklamalar

Bu iç yalnızca çekirdek modunda kullanılabilir ve yordam yalnızca bir iç öğe olarak kullanılabilir.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca Bkz.

[Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)