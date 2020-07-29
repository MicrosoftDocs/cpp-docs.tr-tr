---
title: jitintrinsic
ms.date: 11/04/2016
f1_keywords:
- jitintrinsic
- jitintrinsic_cpp
helpviewer_keywords:
- __declspec keyword [C++], jitintrinsic
- jitintrinsic __declspec modifier
ms.assetid: 23dbe416-7ef6-442b-b16d-9a81aab04fa6
ms.openlocfilehash: cecadcad15ee65a44ad5a8245efdb69903c89459
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87233710"
---
# <a name="jitintrinsic"></a>jitintrinsic

İşlevi 64 bit ortak dil çalışma zamanı için önemli olarak işaretler. Bu, Microsoft tarafından sağlanan kitaplıklardaki belirli işlevlerde kullanılır.

## <a name="syntax"></a>Sözdizimi

```
__declspec(jitintrinsic)
```

## <a name="remarks"></a>Açıklamalar

**`jitintrinsic`** işlev imzasına bir MODOPT ( <xref:System.Runtime.CompilerServices.IsJitIntrinsic> ) ekler.

**`__declspec`** Beklenmeyen sonuçlar ortaya çıktığında kullanıcılardan bu değiştirici kullanılması önerilmez.

## <a name="see-also"></a>Ayrıca bkz.

[__declspec](../cpp/declspec.md)<br/>
[Anahtar sözcükler](../cpp/keywords-cpp.md)
