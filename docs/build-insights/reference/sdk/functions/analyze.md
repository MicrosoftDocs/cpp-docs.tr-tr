---
title: Analiz
description: C++ Build Insights SDK 'Sı işlev başvurusunu çözümle.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Analyze
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 5e593b690231adf6f04161f9c3ff6aef3217f9ef
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920326"
---
# <a name="analyze"></a>Analiz

::: moniker range="<=msvc-140"

C++ Build Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio **Sürüm** Seçicisi denetimini visual Studio 2017 veya visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=msvc-150"

`Analyze`İşlevi, bir C++ derlemesini Izlerken MSVC öğesinden alınan bir Windows Için olay izleme (ETW) izlemesi çözümlemek için kullanılır. ETW izlemesinde olaylar, çağıran tarafından belirtilen bir çözümleyici grubuna sırayla iletilir. Bu işlev, olay akışını bir satırda birden çok kez çözümleyici grubuna iletmeyi sağlayan çoklu geçiş analizlerini destekler.

## <a name="syntax"></a>Sözdizimi

```cpp
template <typename... TAnalyzerGroupMembers>
RESULT_CODE Analyze(
    const char*                                   inputLogFile,
    unsigned                                      numberOfPasses,
    StaticAnalyzerGroup<TAnalyzerGroupMembers...> analyzerGroup);

template <typename... TAnalyzerGroupMembers>
RESULT_CODE Analyze(
    const wchar_t*                                inputLogFile,
    unsigned                                      numberOfPasses,
    StaticAnalyzerGroup<TAnalyzerGroupMembers...> analyzerGroup);
```

### <a name="parameters"></a>Parametreler

*TAnalyzerGroupMembers*\
Bu parametre her zaman çıkarılır.

*ınputlogfile*\
Olaylarını okumak istediğiniz giriş ETW izlemesi.

*Numberofgeçişleri*\
Giriş izlemede çalıştırılacak analiz geçişi sayısı. İzleme, her analiz geçişi için belirtilen çözümleyici grubundan bir kez geçirilir.

*Analiz Zergrubu*\
Analiz için kullanılan çözümleyici grubu. Bir çözümleyici grubu oluşturmak için [Makestaticanalizzergroup](make-static-analyzer-group.md) öğesini çağırın. [Makedynamicanalizzergroup](make-dynamic-analyzer-group.md)'tan edinilen dinamik bir çözümleyici grubunu kullanmak için, önce adresini adresine geçirerek bir statik çözümleyici grubu içinde kapsülleyebilirsiniz `MakeStaticAnalyzerGroup` .

### <a name="return-value"></a>Dönüş Değeri

[RESULT_CODE](../other-types/result-code-enum.md) numaralandırmasından elde edilen sonuç kodu.

::: moniker-end
