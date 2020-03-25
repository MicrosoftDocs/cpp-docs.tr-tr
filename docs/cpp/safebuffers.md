---
title: safebuffers
ms.date: 11/04/2016
f1_keywords:
- safebuffers_cpp
helpviewer_keywords:
- __declspec keyword (C++), safebuffers
- safebuffers __declspec keyword
ms.assetid: 0b0dce14-4523-44d2-8070-5dd0fdabc618
ms.openlocfilehash: 705d3eca67f87e505a147af4984496d3af43dd53
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80178918"
---
# <a name="safebuffers"></a>safebuffers

**Microsoft 'a özgü**

Derleyiciye bir işlev için arabellek taşması güvenlik denetimlerini eklememesini bildirir.

## <a name="syntax"></a>Sözdizimi

```
__declspec( safebuffers )
```

## <a name="remarks"></a>Açıklamalar

**/GS** derleyici seçeneği, derleyicinin güvenlik denetimlerini yığına ekleyerek arabellek taşmalarını test etmesine neden olur. Güvenlik denetimleri için uygun olan veri yapılarının türleri [/GS (arabellek güvenlik denetimi)](../build/reference/gs-buffer-security-check.md)bölümünde açıklanmaktadır. Arabellek taşması algılama hakkında daha fazla bilgi için bkz. [MSVC sürümündeki güvenlik özellikleri](https://blogs.msdn.microsoft.com/vcblog/2017/06/28/security-features-in-microsoft-visual-c/).

Uzman düzeyde el ile kod incelemesi veya harici analiz, işlevde arabellek taşması görülmediğini belirleyebilir. Bu durumda, işlev bildirimine **__declspec (safebuffers)** anahtar sözcüğünü uygulayarak bir işlev için güvenlik denetimlerini gizleyebilirsiniz.

> [!CAUTION]
>  Arabellek güvenlik denetimleri, önemli bir güvenlik koruması sağlar ve performans üzerinde göz ardı edilebilir bir etki oluşturur. Bu nedenle, işlev performansının kritik bir önem arz ettiği ve işlevin güvenli olduğunun bilindiği nadir durumlar haricinde bunları engellememenizi öneririz.

## <a name="inline-functions"></a>Satır İçi İşlevler

*Birincil bir işlev* , bir *İkincil işlevin*kopyasını eklemek için bir [ıntıl](inline-functions-cpp.md) anahtar sözcüğü kullanabilir. **__Declspec (safebuffers)** anahtar sözcüğü bir işleve uygulanırsa, bu işlev için arabellek taşması algılama bastırılır. Ancak, ıntıl aşağıdaki yollarla **__declspec (safebuffers)** anahtar sözcüğünü etkiler.

**/GS** derleyici seçeneğinin her iki işlev için de belirtildiğini varsayalım, ancak birincil işlev **__declspec (safebuffers)** anahtar sözcüğünü belirtir. İkincil işlevdeki veri yapıları, bunu güvenlik denetimleri için uygun hale getirir ve işlev bu denetimleri engellemez. Bu durumda:

- Derleyicinin en iyi duruma getirmelerinden bağımsız olarak işlevin satır içi olarak çalışmasını zorlamak için ikincil işlevde [__forceinline](inline-functions-cpp.md) anahtar sözcüğünü belirtin.

- İkincil işlev güvenlik denetimleri için uygun olduğundan, güvenlik denetimleri, **__declspec (safebuffers)** anahtar sözcüğünü belirtse de birincil işleve de uygulanır.

## <a name="example"></a>Örnek

Aşağıdaki kod **__declspec (safebuffers)** anahtar sözcüğünün nasıl kullanılacağını gösterir.

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
[Anahtar Sözcükler](../cpp/keywords-cpp.md)<br/>
[satır içi, __inline, \__forceinline](inline-functions-cpp.md)<br/>
[strict_gs_check](../preprocessor/strict-gs-check.md)
