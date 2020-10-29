---
title: CompilerPass sınıfı
description: C++ Build Insights SDK 'Sı CompilerPass sınıf başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- CompilerPass
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: bfbfdc28870a13a9cdb19d0ec050ea2e69fe1208
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920820"
---
# <a name="compilerpass-class"></a>CompilerPass sınıfı

::: moniker range="<=msvc-140"

C++ Build Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio **Sürüm** Seçicisi denetimini visual Studio 2017 veya visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=msvc-150"

`CompilerPass`Sınıfı, [matchevent](../functions/match-event.md), [matcheventınmemberfunction](../functions/match-event-in-member-function.md), [Matcheventstack](../functions/match-event-stack.md)ve [matcheventstackinmemberfunction](../functions/match-event-stack-in-member-function.md) işlevleriyle birlikte kullanılır. Bunu bir [BACK_END_PASS](../event-table.md#back-end-pass) veya [FRONT_END_PASS](../event-table.md#front-end-pass) olayı ile eşleştirmek için kullanın.

## <a name="syntax"></a>Syntax

```cpp
class CompilerPass : public Activity
{
public:
    enum class PassCode
    {
        FRONT_END,
        BACK_END
    };

    CompilerPass(const RawEvent& event);

    PassCode       PassCode() const;
    const wchar_t* InputSourcePath() const;
    const wchar_t* OutputObjectPath() const;
};
```

## <a name="members"></a>Üyeler

Devralınan üyelerin [etkinlik](activity.md) temel sınıfından birlikte, `CompilerPass` sınıfı aşağıdaki üyeleri içerir:

### <a name="constructors"></a>Oluşturucular

[CompilerPass](#compiler-pass)

### <a name="enums"></a>Numaralandırmalar

#### <a name="passcode"></a>Geçiş

|Değer|Açıklama|
|-|-|
|FRONT_END|Ön uç geçişi.|
|BACK_END|Arka uç geçişi.|

### <a name="functions"></a>İşlevler

[Inputsourcepath](#input-source-path)\
[OutputObjectPath](#output-object-path)\
[Geçiş](#pass-code)\

## <a name="compilerpass"></a><a name="compiler-pass"></a> CompilerPass

```cpp
CompilerPass(const RawEvent& event);
```

### <a name="parameters"></a>Parametreler

*olay*\
Bir [BACK_END_PASS](../event-table.md#back-end-pass) veya [FRONT_END_PASS](../event-table.md#front-end-pass) olayı.

## <a name="inputsourcepath"></a><a name="input-source-path"></a> Inputsourcepath

```cpp
const wchar_t* InputSourcePath() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu derleyici geçişi tarafından işlenen giriş kaynak dosyasının mutlak yolu.

## <a name="outputobjectpath"></a><a name="output-object-path"></a> OutputObjectPath

```cpp
const wchar_t* OutputObjectPath() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu derleyici geçişi tarafından üretilen çıkış nesnesi dosyasının mutlak yolu.

## <a name="passcode"></a><a name="pass-code"></a> Geçiş

```cpp
PassCode PassCode() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu CompilerPass nesnesi tarafından hangi derleyici geçişinin temsil edileceğini belirten bir kod.

::: moniker-end
