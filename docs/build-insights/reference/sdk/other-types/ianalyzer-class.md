---
title: Ianalyzer sınıfı
description: C++ Build Insights SDK 'Sı IAnalyzer sınıf başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- IAnalyzer
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 2514dd305a186d1153e9f9d1711bb774ea70cdf9
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92919819"
---
# <a name="ianalyzer-class"></a>Ianalyzer sınıfı

::: moniker range="<=msvc-140"

C++ Build Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio **Sürüm** Seçicisi denetimini visual Studio 2017 veya visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=msvc-150"

`IAnalyzer`Sınıfı, Windows Için olay izleme (ETW) izlemesini analiz etmek için bir arabirim sağlar. [Makedynamicanaliz Zergroup](../functions/make-dynamic-analyzer-group.md), [makedynamicreloggergroup](../functions/make-dynamic-relogger-group.md), [Makestaticanalmergroup](../functions/make-dynamic-analyzer-group.md)ve [makestaticreloggergroup](../functions/make-static-analyzer-group.md) işlevleriyle birlikte kullanılır. Bir `IAnalyzer` çözümleyici veya yeniden günlükçü grubunun parçası olabilecek kendi çözümleyicinizi oluşturmak için temel sınıf olarak kullanın.

## <a name="syntax"></a>Syntax

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

Öğesinden türetilen sınıflar `IAnalyzer` hem çözümleyiciler hem de yeniden oturum defterleri olarak kullanılabilir. Yeniden Günlükçüler olarak kullanıldığında, yeniden günlükçü 'ya özgü işlevler, çözümleyici eşdeğerine yeniden yönlendirilir. Tersi doğru değildir: öğesinden türetilen bir sınıf, `IRelogger` çözümleyici olarak kullanılamaz. Bir regünlükçü grubunda çözümleyici kullanılması ortak bir modeldir. Bir regünlükçü grubunun erken bir konumuna yerleştirildiğinde, bir çözümleyici önceden bilgi işlem yapabilir ve daha sonraki konumlarda yeniden Günlükçüler için kullanılabilir hale getirir.

Geçersiz kılınmayan tüm işlevler için varsayılan dönüş değeri `AnalysisControl::CONTINUE` . Daha fazla bilgi için bkz. [Analysiscontrol](analysis-control-enum-class.md).

## <a name="members"></a>Üyeler

Arabiriminden [Ontraceınfo](irelogger-class.md#on-trace-info) üyesine ek olarak `IRelogger` , `IAnalyzer` sınıfı aşağıdaki üyeleri içerir:

### <a name="destructor"></a>Yok edici

[~ IAnalyzer](#ianalyzer-destructor)

### <a name="functions"></a>İşlevler

[OnBeginAnalysis](#on-begin-analysis)\
[OnBeginAnalysisPass](#on-begin-analysis-pass)\
[OnBeginRelogging](#on-begin-relogging)\
[OnBeginReloggingPass](#on-begin-relogging-pass)\
[OnEndAnalysis](#on-end-analysis)\
[OnEndAnalysisPass](#on-end-analysis-pass)\
[OnEndRelogging](#on-end-relogging)\
[OnEndReloggingPass](#on-end-relogging-pass)\
[OnSimpleEvent](#on-simple-event)\
[OnStartActivity](#on-start-activity)\
[OnStopActivity](#on-stop-activity)

## <a name="ianalyzer"></a><a name="ianalyzer-destructor"></a> ~ IAnalyzer

Ianalyzer sınıfını yok eder.

```cpp
virtual ~IAnalyzer();
```

## <a name="onbeginanalysis"></a><a name="on-begin-analysis"></a> OnBeginAnalysis

Çözümleyici grubunun bir parçası için, bu işlev ilk analiz geçişi başlamadan önce çağırılır. Yeniden Günlükçüler grubunun bir parçası için bu işlev, yeniden günlük geçişi başlamadan önce çağrılır. Aynı yeniden günlüğe kaydetme oturumunun hem çözümleyici hem de yeniden günlükçüsü grubunun bir parçası olan çözümleyiciler için, ilk analiz geçişinin başlaması için bu işlev iki kez çağrılır.

```cpp
virtual AnalysisControl OnBeginAnalysis();
```

### <a name="return-value"></a>Dönüş Değeri

Bir sonraki ne olacağını açıklayan bir [Analysiscontrol](analysis-control-enum-class.md) kodu.

## <a name="onbeginanalysispass"></a><a name="on-begin-analysis-pass"></a> OnBeginAnalysisPass

Çözümleyici grubunun bir parçası için bu işlev her analiz geçişinin başlangıcında çağrılır. Yeniden günlükçü grubunun bir parçası olan çözümleyiciler için, bu işlev yeniden günlükçü geçişinin başlangıcında çağrılır. Aynı yeniden günlüğe kaydetme oturumunun hem çözümleyici hem de yeniden günlükçü grubunun bir parçası olarak, bu işlev her analiz geçişinin başlangıcında ve yeniden günlükçü geçişinin başlangıcında çağrılır.

```cpp
virtual AnalysisControl OnBeginAnalysisPass();
```

### <a name="return-value"></a>Dönüş Değeri

Bir sonraki ne olacağını açıklayan bir [Analysiscontrol](analysis-control-enum-class.md) kodu.

## <a name="onbeginrelogging"></a><a name="on-begin-relogging"></a> OnBeginRelogging

```cpp
AnalysisControl OnBeginRelogging() final;
```

Bu işlev geçersiz kılınamıyor. Çözümleyici bir regünlükçü grubunun parçası olduğunda C++ Build Insights SDK 'Sı tarafından çağrılır. Bu işlev, [Onbeginanalysis](#on-begin-analysis)çağrısını yeniden yönlendirir.

### <a name="return-value"></a>Dönüş Değeri

[Onbeginanalysis](#on-begin-analysis) çağrısının sonucu.

## <a name="onbeginreloggingpass"></a><a name="on-begin-relogging-pass"></a> OnBeginReloggingPass

Bu işlev geçersiz kılınamıyor. Çözümleyici bir regünlükçü grubunun parçası olduğunda C++ Build Insights SDK 'Sı tarafından çağrılır. Bu işlev, [Onbeginanalysispass](#on-begin-analysis-pass)çağrısını yeniden yönlendirir.

```cpp
AnalysisControl OnBeginReloggingPass() final;
```

### <a name="return-value"></a>Dönüş Değeri

[Onbeginanalysispass](#on-begin-analysis-pass) çağrısının sonucu.

## <a name="onendanalysis"></a><a name="on-end-analysis"></a> OnEndAnalysis

Bir çözümleyici grubunun parçası olan çözümleyiciler için, bu işlev son analiz geçişi sona erdikten sonra çağrılır. Bir regünlükçü grubunun parçası olan çözümleyiciler için, bu işlev yeniden günlüğe kaydetme geçişinin sona erdikten sonra çağrılır. Aynı yeniden günlüğe kaydetme oturumunun hem çözümleyici hem de yeniden günlükçüsü grubunun parçası olan çözümleyiciler için, bu işlev iki kez çağrılır:

1. tüm analiz geçişleri sona erdikten ve yeniden günlüğe kaydetme geçişi başlamadan önce ve
1. yeniden günlüğe kaydetme geçişi sona erdikten sonra.

```cpp
virtual AnalysisControl OnEndAnalysis();
```

### <a name="return-value"></a>Dönüş Değeri

Bir sonraki ne olacağını açıklayan bir [Analysiscontrol](analysis-control-enum-class.md) kodu.

## <a name="onendanalysispass"></a><a name="on-end-analysis-pass"></a> OnEndAnalysisPass

Çözümleyici grubunun bir parçası için bu işlev her analiz geçişinin sonunda çağırılır. Yeniden günlükçü grubunun bir parçası olan çözümleyiciler için, bu işlev yeniden günlükçü geçişinin sonunda çağırılır. Aynı yeniden günlüğe kaydetme oturumunun hem çözümleyici hem de yeniden günlükçü grubunun bir parçası olarak, bu işlev her analiz geçişinin sonunda ve yeniden günlükçü geçişinin sonunda çağırılır.

```cpp
virtual AnalysisControl OnEndAnalysisPass();
```

### <a name="return-value"></a>Dönüş Değeri

Bir sonraki ne olacağını açıklayan bir [Analysiscontrol](analysis-control-enum-class.md) kodu.

## <a name="onendrelogging"></a><a name="on-end-relogging"></a> OnEndRelogging

Bu işlev geçersiz kılınamıyor. Çözümleyici bir regünlükçü grubunun parçası olduğunda C++ Build Insights SDK 'Sı tarafından çağrılır. Bu işlev, [OnEndAnalysis](#on-end-analysis)çağrısını yeniden yönlendirir.

```cpp
AnalysisControl OnEndRelogging() final;
```

### <a name="return-value"></a>Dönüş Değeri

[OnEndAnalysis](#on-end-analysis) çağrısının sonucu.

## <a name="onendreloggingpass"></a><a name="on-end-relogging-pass"></a> OnEndReloggingPass

Bu işlev geçersiz kılınamıyor. Çözümleyici bir regünlükçü grubunun parçası olduğunda C++ Build Insights SDK 'Sı tarafından çağrılır. Bu işlev, [OnEndAnalysisPass](#on-end-analysis-pass)çağrısını yeniden yönlendirir.

```cpp
AnalysisControl OnEndReloggingPass() final;
```

### <a name="return-value"></a>Dönüş Değeri

[OnEndAnalysisPass](#on-end-analysis-pass) çağrısının sonucu.

## <a name="onsimpleevent"></a><a name="on-simple-event"></a> OnSimpleEvent

Bu işlev, basit bir olay işlendiğinde çağrılır. Bu işlevin ikinci sürümü geçersiz kılınamaz. Çözümleyici bir regünlükçü grubunun parçası olduğunda C++ Build Insights SDK 'Sı tarafından çağrılır. Sürüm 2 ' ye yapılan tüm çağrılar 1. sürüme yeniden yönlendirilir.

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
Bu basit olay için olay yığını. Olay yığınları hakkında daha fazla bilgi için bkz. [Olaylar](../event-table.md).

*relogSession*\
Bu parametre kullanılmıyor.

### <a name="return-value"></a>Dönüş Değeri

Bir sonraki ne olacağını açıklayan bir [Analysiscontrol](analysis-control-enum-class.md) kodu.

## <a name="onstartactivity"></a><a name="on-start-activity"></a> OnStartActivity

Bu işlev, etkinlik başlatma olayı işlendiğinde çağrılır. Bu işlevin ikinci sürümü geçersiz kılınamaz. Çözümleyici bir regünlükçü grubunun parçası olduğunda C++ Build Insights SDK 'Sı tarafından çağrılır. Sürüm 2 ' ye yapılan tüm çağrılar 1. sürüme yeniden yönlendirilir.

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
Bu etkinlik başlangıç olayı için olay yığını. Olay yığınları hakkında daha fazla bilgi için bkz. [Olaylar](../event-table.md).

*relogSession*\
Bu parametre kullanılmıyor.

### <a name="return-value"></a>Dönüş Değeri

Bir sonraki ne olacağını açıklayan bir [Analysiscontrol](analysis-control-enum-class.md) kodu.

## <a name="onstopactivity"></a><a name="on-stop-activity"></a> OnStopActivity

Bu işlev, etkinlik durdurma olayı işlendiğinde çağrılır. Bu işlevin ikinci sürümü geçersiz kılınamaz. Çözümleyici bir regünlükçü grubunun parçası olduğunda C++ Build Insights SDK 'Sı tarafından çağrılır. Sürüm 2 ' ye yapılan tüm çağrılar 1. sürüme yeniden yönlendirilir.

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
Bu etkinlik için olay yığını durdurma olayı. Olay yığınları hakkında daha fazla bilgi için bkz. [Olaylar](../event-table.md).

*relogSession*\
Bu parametre kullanılmıyor.

### <a name="return-value"></a>Dönüş Değeri

Bir sonraki ne olacağını açıklayan bir [Analysiscontrol](analysis-control-enum-class.md) kodu.

::: moniker-end
