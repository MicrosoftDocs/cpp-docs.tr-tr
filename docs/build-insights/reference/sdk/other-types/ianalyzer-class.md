---
title: IAnalyzer sınıfı
description: C++ Build Insights SDK IAnalyzer sınıfı referans.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- IAnalyzer
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: be9d80bb94450458c73fd6ce8d908985ba6f293d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329182"
---
# <a name="ianalyzer-class"></a>IAnalyzer sınıfı

::: moniker range="<=vs-2015"

C++ Build Insights SDK, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlere ait belgeleri görmek için, bu makalenin Visual Studio **Sürüm** seçici denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=vs-2017"

Sınıf, `IAnalyzer` Windows (ETW) izleme için bir Olay İzleme çözümleme için bir arabirim sağlar. [MakeDynamicAnalyzerGroup](../functions/make-dynamic-analyzer-group.md), [MakeDynamicReloggerGroup](../functions/make-dynamic-relogger-group.md), [MakeStaticAnalyzerGroup](../functions/make-dynamic-analyzer-group.md), ve [MakeStaticReloggerGroup](../functions/make-static-analyzer-group.md) fonksiyonları ile kullanılır. Bir `IAnalyzer` çözümleyici veya relogger grubunun bir parçası olabilir kendi çözümleyici oluşturmak için bir taban sınıf olarak kullanın.

## <a name="syntax"></a>Sözdizimi

```cpp
class IAnalyzer : public IRelogger
{
public:
    virtual AnalysisControl OnStartActivity(const EventStack& eventStack);
    virtual AnalysisControl OnStopActivity(const EventStack& eventStack)
    virtual AnalysisControl OnSimpleEvent(const EventStack& eventStack);
    virtual AnalysisControl OnBeginAnalysis();
    virtual AnalysisControl OnEndAnalysis();
    virtual AnalysisControl OnBeginAnalysisPass();
    virtual AnalysisControl OnEndAnalysisPass();

    AnalysisControl OnStartActivity(const EventStack& eventStack,
        const void* relogSession) final;

    AnalysisControl OnStopActivity(const EventStack& eventStack,
        const void* relogSession) final;

    AnalysisControl OnSimpleEvent(const EventStack& eventStack,
        const void* relogSession) final;

    AnalysisControl OnBeginRelogging() final;
    AnalysisControl OnEndRelogging() final;
    AnalysisControl OnBeginReloggingPass() final;
    AnalysisControl OnEndReloggingPass() final;

    virtual ~IAnalyzer();
};
```

## <a name="remarks"></a>Açıklamalar

Bu tür `IAnalyzer` sınıflar hem çözümleyiciler hem de relogger olarak kullanılabilir. Relogger olarak kullanıldığında, relogger özgül işlevleri çözümleyici eşdeğeryönlendirme. Tersi doğru değildir: türeyen `IRelogger` bir sınıf çözümleyici olarak kullanılamaz. Relogger grubunda bir çözümleyici kullanmak yaygın bir desendir. Bir relogger grubunun erken bir konumuna yerleştirildiğinde, bir çözümleyici bilgileri önceden hesaplayabilir ve daha sonraki konumlarda relogger'lar için kullanılabilir hale getirebilir.

Geçersiz kılınan tüm işlevler için varsayılan iade `AnalysisControl::CONTINUE`değeri. Daha fazla bilgi için [AnalysisControl'e](analysis-control-enum-class.md)bakın.

## <a name="members"></a>Üyeler

Arabirimdeki [OnTraceInfo](irelogger-class.md#on-trace-info) üyesine `IRelogger` ek `IAnalyzer` olarak, sınıf aşağıdaki üyeleri içerir:

### <a name="destructor"></a>Yok edici

[~IAnalyzer](#ianalyzer-destructor)

### <a name="functions"></a>İşlevler

[OnbeginAnalysis](#on-begin-analysis)\
[OnbeginAnalysisPass](#on-begin-analysis-pass)\
[OnBeginRelogging](#on-begin-relogging)\
[OnBeginReloggingPass](#on-begin-relogging-pass)\
[OnendAnalysis](#on-end-analysis)\
[OnendAnalysisPass](#on-end-analysis-pass)\
[OnEndRelogging](#on-end-relogging)\
[OnEndReloggingPass](#on-end-relogging-pass)\
[OnSimpleEvent](#on-simple-event)\
[OnstartActivity](#on-start-activity)\
[OnstopAktivite](#on-stop-activity)

## <a name="ianalyzer"></a><a name="ianalyzer-destructor"></a>~IAnalyzer

IAnalyzer sınıfını yok eder.

```cpp
virtual ~IAnalyzer();
```

## <a name="onbeginanalysis"></a><a name="on-begin-analysis"></a>OnbeginAnalysis

Çözümleyici grubunun çözümleyici kısmı için, bu işlev ilk çözümleme geçişi başlamadan önce çağrılır. Bir relogger grubunun çözümleyici bölümü için, bu işlev yeniden günleme geçişi başlamadan önce çağrılır. Aynı yeniden ağaçlandırma oturumunun hem çözümleyici hem de relogger grubunun çözümleyici leri için bu işlev, ilk çözümleme geçişi başlamadan önce iki kez çağrılır.

```cpp
virtual AnalysisControl OnBeginAnalysis();
```

### <a name="return-value"></a>Dönüş Değeri

Bundan sonra ne olması gerektiğini açıklayan bir [AnalysisControl](analysis-control-enum-class.md) kodu.

## <a name="onbeginanalysispass"></a><a name="on-begin-analysis-pass"></a>OnbeginAnalysisPass

Çözümleyici grubunun çözümleyici kısmı için, bu işlev her çözümleme geçişinin başında çağrılır. Bir relogger grubunun çözümleyici bölümü için, bu işlev relogger pass başında denir. Aynı relogging oturumunun hem çözümleyici hem de relogger grubunun çözümleyici kısmı için, bu işlev her analiz geçişinin başında ve relogger geçişinin başında çağrılır.

```cpp
virtual AnalysisControl OnBeginAnalysisPass();
```

### <a name="return-value"></a>Dönüş Değeri

Bundan sonra ne olması gerektiğini açıklayan bir [AnalysisControl](analysis-control-enum-class.md) kodu.

## <a name="onbeginrelogging"></a><a name="on-begin-relogging"></a>OnBeginRelogging

```cpp
AnalysisControl OnBeginRelogging() final;
```

Bu işlev geçersiz kılınamaz. Bir çözümleyici bir relogger grubunun bir parçası olduğunda C++ Build Insights SDK tarafından çağrılır. Bu işlev çağrıyı [OnBeginAnalysis'e](#on-begin-analysis)yönlendirir.

### <a name="return-value"></a>Dönüş Değeri

[OnBeginAnalysis](#on-begin-analysis) çağrısının sonucu.

## <a name="onbeginreloggingpass"></a><a name="on-begin-relogging-pass"></a>OnBeginReloggingPass

Bu işlev geçersiz kılınamaz. Bir çözümleyici bir relogger grubunun bir parçası olduğunda C++ Build Insights SDK tarafından çağrılır. Bu işlev çağrıyı [OnBeginAnalysisPass'e](#on-begin-analysis-pass)yönlendirir.

```cpp
AnalysisControl OnBeginReloggingPass() final;
```

### <a name="return-value"></a>Dönüş Değeri

[OnBeginAnalysisPass](#on-begin-analysis-pass) aramasonucu.

## <a name="onendanalysis"></a><a name="on-end-analysis"></a>OnendAnalysis

Çözümleyici grubunun bir parçası olan çözümleyiciler için, bu işlev son çözümleme geçişi sona erdikten sonra çağrılır. Bir relogger grubunun parçası olan çözümleyiciler için, bu işlev yeniden günleme geçişi sona erdikten sonra çağrılır. Aynı yeniden günleme oturumunun hem çözümleyici hem de relogger grubunun bir parçası olan çözümleyiciler için bu işlev iki kez çağrılır:

1. tüm analiz geçişleri sona erdikten sonra ve yeniden ağaçlama geçişi başlamadan önce ve
1. yeniden ağaçlama geçişi sona erdikten sonra.

```cpp
virtual AnalysisControl OnEndAnalysis();
```

### <a name="return-value"></a>Dönüş Değeri

Bundan sonra ne olması gerektiğini açıklayan bir [AnalysisControl](analysis-control-enum-class.md) kodu.

## <a name="onendanalysispass"></a><a name="on-end-analysis-pass"></a>OnendAnalysisPass

Çözümleyici grubunun çözümleyici kısmı için, bu işlev her çözümleme geçişinin sonunda çağrılır. Bir relogger grubunun çözümleyici bölümü için, bu işlev relogger pass sonunda denir. Aynı relogging oturumunun hem çözümleyici hem de relogger grubunun çözümleyici kısmı için, bu işlev her analiz geçişinin sonunda ve relogger geçişinin sonunda çağrılır.

```cpp
virtual AnalysisControl OnEndAnalysisPass();
```

### <a name="return-value"></a>Dönüş Değeri

Bundan sonra ne olması gerektiğini açıklayan bir [AnalysisControl](analysis-control-enum-class.md) kodu.

## <a name="onendrelogging"></a><a name="on-end-relogging"></a>OnEndRelogging

Bu işlev geçersiz kılınamaz. Bir çözümleyici bir relogger grubunun bir parçası olduğunda C++ Build Insights SDK tarafından çağrılır. Bu işlev aramayı [OnEndAnalysis'e](#on-end-analysis)yönlendirir.

```cpp
AnalysisControl OnEndRelogging() final;
```

### <a name="return-value"></a>Dönüş Değeri

[OnEndAnalysis](#on-end-analysis) çağrısının sonucu.

## <a name="onendreloggingpass"></a><a name="on-end-relogging-pass"></a>OnEndReloggingPass

Bu işlev geçersiz kılınamaz. Bir çözümleyici bir relogger grubunun bir parçası olduğunda C++ Build Insights SDK tarafından çağrılır. Bu işlev aramayı [OnEndAnalysisPass'e](#on-end-analysis-pass)yönlendirir.

```cpp
AnalysisControl OnEndReloggingPass() final;
```

### <a name="return-value"></a>Dönüş Değeri

[OnEndAnalysisPass](#on-end-analysis-pass) aramasının sonucu.

## <a name="onsimpleevent"></a><a name="on-simple-event"></a>OnSimpleEvent

Basit bir olay işlenirken bu işlev çağrılır. Bu işlevin ikinci sürümü geçersiz kılınamaz. Bir çözümleyici bir relogger grubunun bir parçası olduğunda C++ Build Insights SDK tarafından çağrılır. Sürüm 2'ye yapılan tüm aramalar sürüm 1'e yönlendirilir.

### <a name="version-1"></a>Sürüm 1

```cpp
virtual AnalysisControl OnSimpleEvent(const EventStack& eventStack);
```

### <a name="version-2"></a>Sürüm 2

```cpp
AnalysisControl OnSimpleEvent(const EventStack& eventStack,
        const void* relogSession) final;
```

### <a name="parameters"></a>Parametreler

*eventStack*\
Bu basit olay için olay yığını. Olay yığınları hakkında daha fazla bilgi için [Etkinlikler'e](../event-table.md)bakın.

*relogSession*\
Bu parametre kullanılmaz.

### <a name="return-value"></a>Dönüş Değeri

Bundan sonra ne olması gerektiğini açıklayan bir [AnalysisControl](analysis-control-enum-class.md) kodu.

## <a name="onstartactivity"></a><a name="on-start-activity"></a>OnstartActivity

Bu işlev, bir etkinlik başlangıç olayı işlenirken çağrılır. Bu işlevin ikinci sürümü geçersiz kılınamaz. Bir çözümleyici bir relogger grubunun bir parçası olduğunda C++ Build Insights SDK tarafından çağrılır. Sürüm 2'ye yapılan tüm aramalar sürüm 1'e yönlendirilir.

### <a name="version-1"></a>Sürüm 1

```cpp
virtual AnalysisControl OnStartActivity(const EventStack& eventStack);
```

### <a name="version-2"></a>Sürüm 2

```cpp
AnalysisControl OnStartActivity(const EventStack& eventStack,
        const void* relogSession) final;
```

### <a name="parameters"></a>Parametreler

*eventStack*\
Bu etkinlik başlangıç olayı için olay yığını. Olay yığınları hakkında daha fazla bilgi için [Etkinlikler'e](../event-table.md)bakın.

*relogSession*\
Bu parametre kullanılmaz.

### <a name="return-value"></a>Dönüş Değeri

Bundan sonra ne olması gerektiğini açıklayan bir [AnalysisControl](analysis-control-enum-class.md) kodu.

## <a name="onstopactivity"></a><a name="on-stop-activity"></a>OnstopAktivite

Bu işlev, bir etkinlik durdurma olayı işlenirken çağrılır. Bu işlevin ikinci sürümü geçersiz kılınamaz. Bir çözümleyici bir relogger grubunun bir parçası olduğunda C++ Build Insights SDK tarafından çağrılır. Sürüm 2'ye yapılan tüm aramalar sürüm 1'e yönlendirilir.

### <a name="version-1"></a>Sürüm 1

```cpp
virtual AnalysisControl OnStopActivity(const EventStack& eventStack);
```

### <a name="version-2"></a>Sürüm 2

```cpp
AnalysisControl OnStopActivity(const EventStack& eventStack,
        const void* relogSession) final;
```

### <a name="parameters"></a>Parametreler

*eventStack*\
Bu etkinlik durdurma olayı için olay yığını. Olay yığınları hakkında daha fazla bilgi için [Etkinlikler'e](../event-table.md)bakın.

*relogSession*\
Bu parametre kullanılmaz.

### <a name="return-value"></a>Dönüş Değeri

Bundan sonra ne olması gerektiğini açıklayan bir [AnalysisControl](analysis-control-enum-class.md) kodu.

::: moniker-end
