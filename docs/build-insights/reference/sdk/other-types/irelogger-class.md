---
title: Iregünlükçü sınıfı
description: C++ derleme öngörüleri SDK ıregünlükçü sınıfı başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- IRelogger
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: e504ece95529f7279650062145f3ac0914449c98
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92922514"
---
# <a name="irelogger-class"></a>Iregünlükçü sınıfı

::: moniker range="<=msvc-140"

C++ Build Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio **Sürüm** Seçicisi denetimini visual Studio 2017 veya visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=msvc-150"

`IRelogger`Sınıfı, Windows Için olay izleme (ETW) izlemesini yeniden günlüğe kaydetmek için bir arabirim sağlar. [Makedynamicreloggergroup](../functions/make-dynamic-relogger-group.md) ve [Makestaticreloggergroup](../functions/make-static-analyzer-group.md) işlevleriyle birlikte kullanılır. `IRelogger`Bir yeniden günlükçü grubunun parçası olabilecek kendi yeniden günlüklerinizi oluşturmak için temel sınıf olarak kullanın.

## <a name="syntax"></a>Syntax

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

Geçersiz kılınmayan tüm işlevler için varsayılan dönüş değeri `AnalysisControl::CONTINUE` . Daha fazla bilgi için bkz. [Analysiscontrol](analysis-control-enum-class.md).

## <a name="members"></a>Üyeler

### <a name="destructor"></a>Yok edici

[~ Iregünlükçü](#irelogger-destructor)

### <a name="functions"></a>İşlevler

[OnBeginRelogging](#on-begin-relogging)\
[OnBeginReloggingPass](#on-begin-relogging-pass)\
[OnEndRelogging](#on-end-relogging)\
[OnEndReloggingPass](#on-end-relogging-pass)\
[OnSimpleEvent](#on-simple-event)\
[OnStartActivity](#on-start-activity)\
[OnStopActivity](#on-stop-activity)\
[Ontraceınfo](#on-trace-info)

## <a name="irelogger"></a><a name="irelogger-destructor"></a> ~ Iregünlükçü

Iregünlükçü sınıfını yok eder.

```cpp
virtual ~IRelogger();
```

## <a name="onbeginrelogging"></a><a name="on-begin-relogging"></a> OnBeginRelogging

Bu işlev, yeniden günlük geçişi başlamadan önce çağrılır.

```cpp
virtual AnalysisControl OnBeginRelogging();
```

### <a name="return-value"></a>Dönüş Değeri

Bir sonraki ne olacağını açıklayan bir [Analysiscontrol](analysis-control-enum-class.md) kodu.

## <a name="onbeginreloggingpass"></a><a name="on-begin-relogging-pass"></a> OnBeginReloggingPass

Bu işlev, yeniden oturum açma geçişinin başlangıcında çağrılır.

```cpp
virtual AnalysisControl OnBeginReloggingPass();
```

### <a name="return-value"></a>Dönüş Değeri

Bir sonraki ne olacağını açıklayan bir [Analysiscontrol](analysis-control-enum-class.md) kodu.

## <a name="onendrelogging"></a><a name="on-end-relogging"></a> OnEndRelogging

Bu işlev, yeniden oturum açma geçişi sona erdikten sonra çağrılır.

```cpp
virtual AnalysisControl OnEndRelogging();
```

### <a name="return-value"></a>Dönüş Değeri

Bir sonraki ne olacağını açıklayan bir [Analysiscontrol](analysis-control-enum-class.md) kodu.

## <a name="onendreloggingpass"></a><a name="on-end-relogging-pass"></a> OnEndReloggingPass

Bu işlev, yeniden oturum açma geçişinin sonunda çağırılır.

```cpp
virtual AnalysisControl OnEndReloggingPass();
```

### <a name="return-value"></a>Dönüş Değeri

Bir sonraki ne olacağını açıklayan bir [Analysiscontrol](analysis-control-enum-class.md) kodu.

## <a name="onsimpleevent"></a><a name="on-simple-event"></a> OnSimpleEvent

```cpp
virtual AnalysisControl OnSimpleEvent(const EventStack& eventStack);
```

Bu işlev, basit bir olay işlendiğinde çağrılır.

### <a name="parameters"></a>Parametreler

*eventStack*\
Bu basit olay için olay yığını. Olay yığınları hakkında daha fazla bilgi için bkz. [Olaylar](../event-table.md).

### <a name="return-value"></a>Dönüş Değeri

Bir sonraki ne olacağını açıklayan bir [Analysiscontrol](analysis-control-enum-class.md) kodu.

## <a name="onstartactivity"></a><a name="on-start-activity"></a> OnStartActivity

```cpp
virtual AnalysisControl OnStartActivity(const EventStack& eventStack);
```

Bu işlev, etkinlik başlatma olayı işlendiğinde çağrılır.

### <a name="parameters"></a>Parametreler

*eventStack*\
Bu etkinlik başlangıç olayı için olay yığını. Olay yığınları hakkında daha fazla bilgi için bkz. [Olaylar](../event-table.md).

### <a name="return-value"></a>Dönüş Değeri

Bir sonraki ne olacağını açıklayan bir [Analysiscontrol](analysis-control-enum-class.md) kodu.

## <a name="onstopactivity"></a><a name="on-stop-activity"></a> OnStopActivity

Bu işlev, etkinlik durdurma olayı işlendiğinde çağrılır.

```cpp
virtual AnalysisControl OnStopActivity(const EventStack& eventStack);
```

### <a name="parameters"></a>Parametreler

*eventStack*\
Bu etkinlik için olay yığını durdurma olayı. Olay yığınları hakkında daha fazla bilgi için bkz. [Olaylar](../event-table.md).

### <a name="return-value"></a>Dönüş Değeri

Bir sonraki ne olacağını açıklayan bir [Analysiscontrol](analysis-control-enum-class.md) kodu.

## <a name="ontraceinfo"></a><a name="on-trace-info"></a> Ontraceınfo

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
