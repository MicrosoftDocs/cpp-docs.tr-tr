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
ms.openlocfilehash: 4626ba82d1d24582951bbffd8e6be687007d390f
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80178205"
---
# <a name="jitintrinsic"></a>jitintrinsic

İşlevi 64 bit ortak dil çalışma zamanı için önemli olarak işaretler. Bu, Microsoft tarafından sağlanan kitaplıklardaki belirli işlevlerde kullanılır.

## <a name="syntax"></a>Sözdizimi

```
__declspec(jitintrinsic)
```

## <a name="remarks"></a>Açıklamalar

**jic** , bir işlev imzasına bir MODOPT (<xref:System.Runtime.CompilerServices.IsJitIntrinsic>) ekler.

Bu __declspec değiştiricisinden, kullanıcıların beklenmedik sonuçlar oluşması durumunda bu **__declspec** değiştiricisini kullanmaktan önerilmez.

## <a name="see-also"></a>Ayrıca bkz.

[__declspec](../cpp/declspec.md)<br/>
[Anahtar Sözcükler](../cpp/keywords-cpp.md)
