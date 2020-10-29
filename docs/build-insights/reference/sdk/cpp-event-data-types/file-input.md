---
title: FileInput sınıfı
description: C++ Build Insights SDK 'Sı FileInput sınıfı başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- FileInput
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 6e12336c10347f00ea2663116f2f308658775e0d
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920690"
---
# <a name="fileinput-class"></a>FileInput sınıfı

::: moniker range="<=msvc-140"

C++ Build Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio **Sürüm** Seçicisi denetimini visual Studio 2017 veya visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=msvc-150"

`FileInput`Sınıfı, [matchevent](../functions/match-event.md), [matcheventınmemberfunction](../functions/match-event-in-member-function.md), [Matcheventstack](../functions/match-event-stack.md)ve [matcheventstackinmemberfunction](../functions/match-event-stack-in-member-function.md) işlevleriyle birlikte kullanılır. Bunu bir [FILE_INPUT](../event-table.md#file-input) olayına uyacak şekilde kullanın.

## <a name="syntax"></a>Syntax

```cpp
class FileInput : public SimpleEvent
{
public:
    enum class Type
    {
        OTHER               = FILE_TYPE_CODE_OTHER,
        OBJ                 = FILE_TYPE_CODE_OBJ,
        EXECUTABLE_IMAGE    = FILE_TYPE_CODE_EXECUTABLE_IMAGE,
        LIB                 = FILE_TYPE_CODE_LIB,
        IMP_LIB             = FILE_TYPE_CODE_IMP_LIB,
        EXP                 = FILE_TYPE_CODE_EXP
    };

    FileInput(const RawEvent& event);

    const wchar_t* Path() const;
    Type           Type() const;
};
```

## <a name="members"></a>Üyeler

Devralınan üyelerin [SimpleEvent](simple-event.md) temel sınıfından birlikte, `FileInput` sınıfı aşağıdaki üyeleri içerir:

### <a name="constructors"></a>Oluşturucular

[FileInput](#file-input)

### <a name="functions"></a>İşlevler

[Yol](#path) 
 [Tür](#type)

## <a name="fileinput"></a><a name="file-input"></a> Dosya girişi

```cpp
FileInput(const RawEvent& event);
```

### <a name="parameters"></a>Parametreler

*olay*\
[FILE_INPUT](../event-table.md#file-input) bir olay.

## <a name="path"></a><a name="path"></a> Yolun

```cpp
const wchar_t Path() const;
```

### <a name="return-value"></a>Dönüş Değeri

Giriş dosyasının mutlak yolu.

## <a name="type"></a><a name="type"></a> Türüyle

```cpp
Type Type() const;
```

### <a name="return-value"></a>Dönüş Değeri

Giriş dosyasının türünü tanımlayan bir kod.

::: moniker-end
