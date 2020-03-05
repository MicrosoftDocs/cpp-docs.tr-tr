---
title: Çözümleme
description: C++ Build Insights SDK 'sı Işlev başvurusunu çözümle.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Analyze
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 49161641d1cff1c64261d95bb2caace2f802543a
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78332868"
---
# <a name="analyze"></a>Çözümleme

::: moniker range="<=vs-2015"

Build C++ Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio sürüm Seçicisi denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın.

::: moniker-end
::: moniker range=">=vs-2017"

`Analyze` işlevi, bir C++ DERLEMEYI izlerken MSVC 'ten alınan bir Windows Için olay Izleme (ETW) izlemesi çözümlemek için kullanılır. ETW izlemesinde olaylar, çağıran tarafından belirtilen bir çözümleyici grubuna sırayla iletilir. Bu işlev, olay akışını bir satırda birden çok kez çözümleyici grubuna iletmeyi sağlayan çoklu geçiş analizlerini destekler.

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

*analiz Zergrubu*\
Analiz için kullanılan çözümleyici grubu. Bir çözümleyici grubu oluşturmak için [Makestaticanalizzergroup](make-static-analyzer-group.md) öğesini çağırın. [Makedynamicanalizzergroup](make-dynamic-analyzer-group.md)'tan elde edilen dinamik bir çözümleyici grubunu kullanmak için, önce adresini `MakeStaticAnalyzerGroup`adresine geçirerek bir statik çözümleyici grubu içinde kapsülleyebilirsiniz.

### <a name="return-value"></a>Dönüş Değeri

[RESULT_CODE](../other-types/result-code-enum.md) numaralandırmasından elde edilen sonuç kodu.

::: moniker-end
