---
title: __writecr0
ms.date: 11/04/2016
f1_keywords:
- _writecr0
helpviewer_keywords:
- _writecr0 intrinsic
ms.assetid: a143d08d-0333-4e1b-91b4-4acb2ae91b5a
ms.openlocfilehash: cdc93f178f033b072cad68180dfee305d9bf62a5
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/09/2018
ms.locfileid: "51330534"
---
# <a name="writecr0"></a>__writecr0

**Microsoft'a özgü**

Değeri Yazar `Data` CR0 kaydının kaydı.

## <a name="syntax"></a>Sözdizimi

```
void writecr0(
   unsigned __int64 Data
);
```

#### <a name="parameters"></a>Parametreler

*Veri*<br/>
[in] CR0 kaydının kasaya yazılacak değer.

## <a name="requirements"></a>Gereksinimler

|İç|Mimari|
|---------------|------------------|
|`__writecr0`|x86, x64|

**Üst bilgi dosyası** \<intrin.h >

## <a name="remarks"></a>Açıklamalar

Bu iç yalnızca çekirdek modunda kullanılabilir ve yordam yalnızca bir iç öğe olarak kullanılabilir.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca Bkz.

[Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)