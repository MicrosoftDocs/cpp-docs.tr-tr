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
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62245524"
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