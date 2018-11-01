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
ms.openlocfilehash: 9e726413f0bbfbd9d6affa348777c995c51283a5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50519307"
---
# <a name="jitintrinsic"></a>jitintrinsic

İşlevi 64 bit ortak dil çalışma zamanı için önemli olarak işaretler. Bu, Microsoft tarafından sağlanan kitaplıklardaki belirli işlevlerde kullanılır.

## <a name="syntax"></a>Sözdizimi

```
__declspec(jitintrinsic)
```

## <a name="remarks"></a>Açıklamalar

**jitintrinsic** bir MODOPT ekler (<xref:System.Runtime.CompilerServices.IsJitIntrinsic>) bir işlev imzası.

Kullanıcılar bu kullanarak önerilmez **__declspec** değiştiricisi, beklenmedik sonuçlar oluşabilir.

## <a name="see-also"></a>Ayrıca bkz.

[__declspec](../cpp/declspec.md)<br/>
[Anahtar Sözcükler](../cpp/keywords-cpp.md)