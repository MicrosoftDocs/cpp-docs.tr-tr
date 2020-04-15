---
title: safebuffers
ms.date: 11/04/2016
f1_keywords:
- safebuffers_cpp
helpviewer_keywords:
- __declspec keyword (C++), safebuffers
- safebuffers __declspec keyword
ms.assetid: 0b0dce14-4523-44d2-8070-5dd0fdabc618
ms.openlocfilehash: bc4736ce233ce026ecab9ef38ac8379466b5a0bc
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365580"
---
# <a name="safebuffers"></a>safebuffers

**Microsoft'a Özgü**

Derleyiciye bir işlev için arabellek taşması güvenlik denetimlerini eklememesini bildirir.

## <a name="syntax"></a>Sözdizimi

```
__declspec( safebuffers )
```

## <a name="remarks"></a>Açıklamalar

**/GS** derleyicisi seçeneği, yığına güvenlik denetimleri ekleyerek derleyicinin arabellek taşmaları için test etmesini neden olur. Güvenlik denetimleri için uygun olan veri yapıları türleri [/GS (Arabellek Güvenlik Denetimi)](../build/reference/gs-buffer-security-check.md)olarak açıklanmıştır. Arabellek taşma algılama hakkında daha fazla bilgi [için, MSVC Güvenlik Özellikleri](https://blogs.msdn.microsoft.com/vcblog/2017/06/28/security-features-in-microsoft-visual-c/)bakın.

Uzman düzeyde el ile kod incelemesi veya harici analiz, işlevde arabellek taşması görülmediğini belirleyebilir. Bu durumda, işlev bildirimine **__declspec (safebuffers)** anahtar sözcük lerini uygulayarak işlevin güvenlik denetimlerini bastırabilirsiniz.

> [!CAUTION]
> Arabellek güvenlik denetimleri, önemli bir güvenlik koruması sağlar ve performans üzerinde göz ardı edilebilir bir etki oluşturur. Bu nedenle, işlev performansının kritik bir önem arz ettiği ve işlevin güvenli olduğunun bilindiği nadir durumlar haricinde bunları engellememenizi öneririz.

## <a name="inline-functions"></a>Satır İçi İşlevler

*Birincil işlev,* ikincil bir *işlevin*kopyasını eklemek için [bir inlining](inline-functions-cpp.md) anahtar kelime kullanabilirsiniz. Bir işleve **__declspec (safebuffers)** anahtar sözcüğü uygulanırsa, bu işlev için arabellek çok zoru algılaması bastırılır. Ancak, inlining aşağıdaki yollarla **__declspec (safebuffers)** anahtar sözcük etkiler.

**/GS** derleyicisi seçeneğinin her iki işlev için de belirtildiğini, ancak birincil işlevin **__declspec (safebuffers)** anahtar sözcüğlerini belirlediğini varsayalım. İkincil işlevdeki veri yapıları, bunu güvenlik denetimleri için uygun hale getirir ve işlev bu denetimleri engellemez. Bu durumda:

- Derleyiciyi, derleyici optimizasyonlarından bağımsız olarak bu işlevi satır hizaya zorlamak için ikincil işlevdeki [__forceinline](inline-functions-cpp.md) anahtar sözcüğü belirtin.

- İkincil işlev güvenlik denetimleri için uygun olduğundan, **__declspec (safebuffers)** anahtar sözcük belirtir rağmen güvenlik denetimleri de birincil işlevi uygulanır.

## <a name="example"></a>Örnek

Aşağıdaki kod, **__declspec (safebuffers)** anahtar kelimesinin nasıl kullanılacağını gösterir.

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

**END Microsoft Özel**

## <a name="see-also"></a>Ayrıca bkz.

[__declspec](../cpp/declspec.md)<br/>
[Anahtar sözcükler](../cpp/keywords-cpp.md)<br/>
[satır içinde, \___inline, _forceinline](inline-functions-cpp.md)<br/>
[strict_gs_check](../preprocessor/strict-gs-check.md)
