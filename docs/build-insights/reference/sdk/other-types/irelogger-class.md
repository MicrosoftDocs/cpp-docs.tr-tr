---
title: Iregünlükçü sınıfı
description: C++ Build Insights SDK 'Sı ıregünlükçü sınıfı başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- IRelogger
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: d0796cec3fe4ac6183279e8d8013a9550f18b61c
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78857066"
---
# <a name="irelogger-class"></a>Iregünlükçü sınıfı

::: moniker range="<=vs-2015"

Build C++ Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio sürüm Seçicisi denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın.

::: moniker-end
::: moniker range=">=vs-2017"

`IRelogger` sınıfı, Windows için olay Izleme (ETW) izlemesini yeniden günlüğe kaydetmek için bir arabirim sağlar. [Makedynamicreloggergroup](../functions/make-dynamic-relogger-group.md) ve [Makestaticreloggergroup](../functions/make-static-analyzer-group.md) işlevleriyle birlikte kullanılır. Bir yeniden günlükçü grubunun parçası olabilecek kendi yeniden günlüklerinizi oluşturmak için `IRelogger` temel sınıf olarak kullanın.

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

Geçersiz kılınamayan tüm işlevler için varsayılan dönüş değeri `AnalysisControl::CONTINUE`. Daha fazla bilgi için bkz. [Analysiscontrol](analysis-control-enum-class.md).

## <a name="members"></a>Üyeler

### <a name="destructor"></a>Yok edici

[~ Iregünlükçü](#irelogger-destructor)

### <a name="functions"></a>İşlevler

[Onbeginrelogging](#on-begin-relogging)\
[Onbeginreloggingpass](#on-begin-relogging-pass)\
[OnEndRelogging](#on-end-relogging)\
[OnEndReloggingPass](#on-end-relogging-pass)\
[Onsimpleevent](#on-simple-event)\
[Onstartactivity](#on-start-activity)\
[Onstopactivity](#on-stop-activity)\
[Ontraceınfo](#on-trace-info)

## <a name="irelogger-destructor"></a>~ Iregünlükçü

Iregünlükçü sınıfını yok eder.

```cpp
virtual ~IRelogger();
```

## <a name="on-begin-relogging"></a>OnBeginRelogging

Bu işlev, yeniden günlük geçişi başlamadan önce çağrılır.

```cpp
virtual AnalysisControl OnBeginRelogging();
```

### <a name="return-value"></a>Dönüş Değeri

Bir sonraki ne olacağını açıklayan bir [Analysiscontrol](analysis-control-enum-class.md) kodu.

## <a name="on-begin-relogging-pass"></a>OnBeginReloggingPass

Bu işlev, yeniden oturum açma geçişinin başlangıcında çağrılır.

```cpp
virtual AnalysisControl OnBeginReloggingPass();
```

### <a name="return-value"></a>Dönüş Değeri

Bir sonraki ne olacağını açıklayan bir [Analysiscontrol](analysis-control-enum-class.md) kodu.

## <a name="on-end-relogging"></a>OnEndRelogging

Bu işlev, yeniden oturum açma geçişi sona erdikten sonra çağrılır.

```cpp
virtual AnalysisControl OnEndRelogging();
```

### <a name="return-value"></a>Dönüş Değeri

Bir sonraki ne olacağını açıklayan bir [Analysiscontrol](analysis-control-enum-class.md) kodu.

## <a name="on-end-relogging-pass"></a>OnEndReloggingPass

Bu işlev, yeniden oturum açma geçişinin sonunda çağırılır.

```cpp
virtual AnalysisControl OnEndReloggingPass();
```

### <a name="return-value"></a>Dönüş Değeri

Bir sonraki ne olacağını açıklayan bir [Analysiscontrol](analysis-control-enum-class.md) kodu.

## <a name="on-simple-event"></a>OnSimpleEvent

```cpp
virtual AnalysisControl OnSimpleEvent(const EventStack& eventStack);
```

Bu işlev, basit bir olay işlendiğinde çağrılır.

### <a name="parameters"></a>Parametreler

*Eventstack*\
Bu basit olay için olay yığını. Olay yığınları hakkında daha fazla bilgi için bkz. [Olaylar](../event-table.md).

### <a name="return-value"></a>Dönüş Değeri

Bir sonraki ne olacağını açıklayan bir [Analysiscontrol](analysis-control-enum-class.md) kodu.

## <a name="on-start-activity"></a>OnStartActivity

```cpp
virtual AnalysisControl OnStartActivity(const EventStack& eventStack);
```

Bu işlev, etkinlik başlatma olayı işlendiğinde çağrılır.

### <a name="parameters"></a>Parametreler

*Eventstack*\
Bu etkinlik başlangıç olayı için olay yığını. Olay yığınları hakkında daha fazla bilgi için bkz. [Olaylar](../event-table.md).

### <a name="return-value"></a>Dönüş Değeri

Bir sonraki ne olacağını açıklayan bir [Analysiscontrol](analysis-control-enum-class.md) kodu.

## <a name="on-stop-activity"></a>OnStopActivity

Bu işlev, etkinlik durdurma olayı işlendiğinde çağrılır.

```cpp
virtual AnalysisControl OnStopActivity(const EventStack& eventStack);
```

### <a name="parameters"></a>Parametreler

*Eventstack*\
Bu etkinlik için olay yığını durdurma olayı. Olay yığınları hakkında daha fazla bilgi için bkz. [Olaylar](../event-table.md).

### <a name="return-value"></a>Dönüş Değeri

Bir sonraki ne olacağını açıklayan bir [Analysiscontrol](analysis-control-enum-class.md) kodu.

## <a name="on-trace-info"></a>Ontraceınfo

```cpp
virtual AnalysisControl OnTraceInfo(const TraceInfo& traceInfo);
```

Bu işlev, her analiz veya yeniden oturum açma geçişinin başlangıcında bir kez çağrılır.

### <a name="parameters"></a>Parametreler

*TraceInfo*\
Tüketilmekte olan izleme hakkında faydalı özellikler içeren bir [TraceInfo](../cpp-event-data-types/trace-info.md) nesnesi.

### <a name="return-value"></a>Dönüş Değeri

Bir sonraki ne olacağını açıklayan bir [Analysiscontrol](analysis-control-enum-class.md) kodu.

::: moniker-end
