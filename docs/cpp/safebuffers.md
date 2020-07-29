---
title: safebuffers
ms.date: 11/04/2016
f1_keywords:
- safebuffers_cpp
helpviewer_keywords:
- __declspec keyword (C++), safebuffers
- safebuffers __declspec keyword
ms.assetid: 0b0dce14-4523-44d2-8070-5dd0fdabc618
ms.openlocfilehash: 456e84cfba40a4219f44fe1549272621f79d09a2
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87213248"
---
# <a name="safebuffers"></a>safebuffers

**Microsoft'a Özgü**

Derleyiciye bir işlev için arabellek taşması güvenlik denetimlerini eklememesini bildirir.

## <a name="syntax"></a>Sözdizimi

```
__declspec( safebuffers )
```

## <a name="remarks"></a>Açıklamalar

**/GS** derleyici seçeneği, derleyicinin güvenlik denetimlerini yığına ekleyerek arabellek taşmalarını test etmesine neden olur. Güvenlik denetimleri için uygun olan veri yapılarının türleri [/GS (arabellek güvenlik denetimi)](../build/reference/gs-buffer-security-check.md)bölümünde açıklanmaktadır. Arabellek taşması algılama hakkında daha fazla bilgi için bkz. [MSVC sürümündeki güvenlik özellikleri](https://devblogs.microsoft.com/cppblog/security-features-in-microsoft-visual-c/).

Uzman düzeyde el ile kod incelemesi veya harici analiz, işlevde arabellek taşması görülmediğini belirleyebilir. Bu durumda, **`__declspec(safebuffers)`** işlev bildirimine anahtar sözcüğünü uygulayarak bir işlev için güvenlik denetimlerini gizleyebilirsiniz.

> [!CAUTION]
> Arabellek güvenlik denetimleri, önemli bir güvenlik koruması sağlar ve performans üzerinde göz ardı edilebilir bir etki oluşturur. Bu nedenle, işlev performansının kritik bir önem arz ettiği ve işlevin güvenli olduğunun bilindiği nadir durumlar haricinde bunları engellememenizi öneririz.

## <a name="inline-functions"></a>Satır İçi İşlevler

*Birincil bir işlev* , bir *İkincil işlevin*kopyasını eklemek için bir [ıntıl](inline-functions-cpp.md) anahtar sözcüğü kullanabilir. **`__declspec(safebuffers)`** Anahtar sözcüğü bir işleve uygulanmışsa, bu işlev için arabellek taşması algılama bastırılır. Ancak, ıntıl, **`__declspec(safebuffers)`** anahtar sözcüğünü aşağıdaki yollarla etkiler.

**/GS** derleyici seçeneğinin her iki işlev için de belirtildiğini varsayalım, ancak birincil işlev **`__declspec(safebuffers)`** anahtar sözcüğünü belirtiyor. İkincil işlevdeki veri yapıları, bunu güvenlik denetimleri için uygun hale getirir ve işlev bu denetimleri engellemez. Bu durumda:

- Derleyicinin en iyi duruma getirmelerinden bağımsız olarak işlevin satır içi olarak çalışmasını zorlamak için ikincil işlevde [__forceinline](inline-functions-cpp.md) anahtar sözcüğünü belirtin.

- İkincil işlev güvenlik denetimleri için uygun olduğundan, anahtar sözcüğünü belirtse de, güvenlik denetimleri birincil işleve de uygulanır **`__declspec(safebuffers)`** .

## <a name="example"></a>Örnek

Aşağıdaki kod, anahtar sözcüğünün nasıl kullanılacağını gösterir **`__declspec(safebuffers)`** .

```cpp
// compile with: /c /GS
typedef struct {
    int x[20];
} BUFFER;
static int checkBuffers() {
    BUFFER cb;
    // Use the buffer...
    return 0;
};
static __declspec(safebuffers)
    int noCheckBuffers() {
    BUFFER ncb;
    // Use the buffer...
    return 0;
}
int wmain() {
    checkBuffers();
    noCheckBuffers();
    return 0;
}
```

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[__declspec](../cpp/declspec.md)<br/>
[Anahtar sözcükler](../cpp/keywords-cpp.md)<br/>
[satır içi, __inline, \_ _forceinline](inline-functions-cpp.md)<br/>
[strict_gs_check](../preprocessor/strict-gs-check.md)
