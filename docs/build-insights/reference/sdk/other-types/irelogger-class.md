---
title: IRelogger sınıfı
description: C++ Build Insights SDK IRelogger sınıf başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- IRelogger
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 146377b2b44df43ed4b2f749efd9fb614a2a09c9
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329152"
---
# <a name="irelogger-class"></a>IRelogger sınıfı

::: moniker range="<=vs-2015"

C++ Build Insights SDK, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlere ait belgeleri görmek için, bu makalenin Visual Studio **Sürüm** seçici denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=vs-2017"

Sınıf, `IRelogger` Windows (ETW) izleme için olay izlemeyi yeniden günlüğe kaydetmeye yönelik bir arabirim sağlar. [MakeDynamicReloggerGroup](../functions/make-dynamic-relogger-group.md) ve [MakeStaticReloggerGroup](../functions/make-static-analyzer-group.md) işlevleri ile kullanılır. Bir `IRelogger` relogger grubunun parçası olabilir kendi relogger oluşturmak için bir taban sınıf olarak kullanın.

## <a name="syntax"></a>Sözdizimi

```cpp
class IRelogger
{
public:
    virtual AnalysisControl OnStartActivity(const EventStack& eventStack,
        const void* relogSession);

    virtual AnalysisControl OnStopActivity(const EventStack& eventStack,
        const void* relogSession);

    virtual AnalysisControl OnSimpleEvent(const EventStack& eventStack,
        const void* relogSession);

    virtual AnalysisControl OnTraceInfo(const TraceInfo& traceInfo);
    virtual AnalysisControl OnBeginRelogging();
    virtual AnalysisControl OnEndRelogging();
    virtual AnalysisControl OnBeginReloggingPass();
    virtual AnalysisControl OnEndReloggingPass() ;

    virtual ~IRelogger();
};
```

## <a name="remarks"></a>Açıklamalar

Geçersiz kılınan tüm işlevler için varsayılan iade `AnalysisControl::CONTINUE`değeri. Daha fazla bilgi için [AnalysisControl'e](analysis-control-enum-class.md)bakın.

## <a name="members"></a>Üyeler

### <a name="destructor"></a>Yok edici

[~IRelogger](#irelogger-destructor)

### <a name="functions"></a>İşlevler

[OnBeginRelogging](#on-begin-relogging)\
[OnBeginReloggingPass](#on-begin-relogging-pass)\
[OnEndRelogging](#on-end-relogging)\
[OnEndReloggingPass](#on-end-relogging-pass)\
[OnSimpleEvent](#on-simple-event)\
[OnstartActivity](#on-start-activity)\
[OnstopAktivite](#on-stop-activity)\
[OnTraceInfo](#on-trace-info)

## <a name="irelogger"></a><a name="irelogger-destructor"></a>~IRelogger

IRelogger sınıfını yok eder.

```cpp
virtual ~IRelogger();
```

## <a name="onbeginrelogging"></a><a name="on-begin-relogging"></a>OnBeginRelogging

Bu işlev, yeniden günlüğe kaydetme geçişi başlamadan önce çağrılır.

```cpp
virtual AnalysisControl OnBeginRelogging();
```

### <a name="return-value"></a>Dönüş Değeri

Bundan sonra ne olması gerektiğini açıklayan bir [AnalysisControl](analysis-control-enum-class.md) kodu.

## <a name="onbeginreloggingpass"></a><a name="on-begin-relogging-pass"></a>OnBeginReloggingPass

Bu işlev, yeniden günlüğe kaydetme geçişinin başında çağrılır.

```cpp
virtual AnalysisControl OnBeginReloggingPass();
```

### <a name="return-value"></a>Dönüş Değeri

Bundan sonra ne olması gerektiğini açıklayan bir [AnalysisControl](analysis-control-enum-class.md) kodu.

## <a name="onendrelogging"></a><a name="on-end-relogging"></a>OnEndRelogging

Bu işlev, yeniden günlüğe kaydetme geçişi sona erdikten sonra çağrılır.

```cpp
virtual AnalysisControl OnEndRelogging();
```

### <a name="return-value"></a>Dönüş Değeri

Bundan sonra ne olması gerektiğini açıklayan bir [AnalysisControl](analysis-control-enum-class.md) kodu.

## <a name="onendreloggingpass"></a><a name="on-end-relogging-pass"></a>OnEndReloggingPass

Bu işlev, yeniden günlüğe kaydetme geçişinin sonunda çağrılır.

```cpp
virtual AnalysisControl OnEndReloggingPass();
```

### <a name="return-value"></a>Dönüş Değeri

Bundan sonra ne olması gerektiğini açıklayan bir [AnalysisControl](analysis-control-enum-class.md) kodu.

## <a name="onsimpleevent"></a><a name="on-simple-event"></a>OnSimpleEvent

```cpp
virtual AnalysisControl OnSimpleEvent(const EventStack& eventStack);
```

Basit bir olay işlenirken bu işlev çağrılır.

### <a name="parameters"></a>Parametreler

*eventStack*\
Bu basit olay için olay yığını. Olay yığınları hakkında daha fazla bilgi için [Etkinlikler'e](../event-table.md)bakın.

### <a name="return-value"></a>Dönüş Değeri

Bundan sonra ne olması gerektiğini açıklayan bir [AnalysisControl](analysis-control-enum-class.md) kodu.

## <a name="onstartactivity"></a><a name="on-start-activity"></a>OnstartActivity

```cpp
virtual AnalysisControl OnStartActivity(const EventStack& eventStack);
```

Bu işlev, bir etkinlik başlangıç olayı işlenirken çağrılır.

### <a name="parameters"></a>Parametreler

*eventStack*\
Bu etkinlik başlangıç olayı için olay yığını. Olay yığınları hakkında daha fazla bilgi için [Etkinlikler'e](../event-table.md)bakın.

### <a name="return-value"></a>Dönüş Değeri

Bundan sonra ne olması gerektiğini açıklayan bir [AnalysisControl](analysis-control-enum-class.md) kodu.

## <a name="onstopactivity"></a><a name="on-stop-activity"></a>OnstopAktivite

Bu işlev, bir etkinlik durdurma olayı işlenirken çağrılır.

```cpp
virtual AnalysisControl OnStopActivity(const EventStack& eventStack);
```

### <a name="parameters"></a>Parametreler

*eventStack*\
Bu etkinlik durdurma olayı için olay yığını. Olay yığınları hakkında daha fazla bilgi için [Etkinlikler'e](../event-table.md)bakın.

### <a name="return-value"></a>Dönüş Değeri

Bundan sonra ne olması gerektiğini açıklayan bir [AnalysisControl](analysis-control-enum-class.md) kodu.

## <a name="ontraceinfo"></a><a name="on-trace-info"></a>OnTraceInfo

```cpp
virtual AnalysisControl OnTraceInfo(const TraceInfo& traceInfo);
```

Bu işlev, her çözümleme nin veya yeniden günlüğe kaydetme geçişinin başında bir kez çağrılır.

### <a name="parameters"></a>Parametreler

*Traceınfo*\
Tüketilen izleme yle ilgili yararlı özellikler içeren bir [TraceInfo](../cpp-event-data-types/trace-info.md) nesnesi.

### <a name="return-value"></a>Dönüş Değeri

Bundan sonra ne olması gerektiğini açıklayan bir [AnalysisControl](analysis-control-enum-class.md) kodu.

::: moniker-end
