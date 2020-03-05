---
title: FileInput sınıfı
description: C++ BUILD Insights SDK FileInput sınıfı başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- FileInput
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: bea2cf72ca2a83a9cd630f8a9ccefb87dd4b7ff1
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78333351"
---
# <a name="fileinput-class"></a>FileInput sınıfı

::: moniker range="<=vs-2015"

Build C++ Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio sürüm Seçicisi denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın.

::: moniker-end
::: moniker range=">=vs-2017"

`FileInput` sınıfı [Matchevent](../functions/match-event.md), [matcheventınmemberfunction](../functions/match-event-in-member-function.md), [Matcheventstack](../functions/match-event-stack.md)ve [matcheventstackinmemberfunction](../functions/match-event-stack-in-member-function.md) işlevleriyle birlikte kullanılır. Bunu bir [FILE_INPUT](../event-table.md#file-input) olayına uyacak şekilde kullanın.

## <a name="syntax"></a>Sözdizimi

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

[SimpleEvent](simple-event.md) temel sınıfından devralınan üyelerle birlikte `FileInput` sınıfı aşağıdaki üyeleri içerir:

### <a name="constructors"></a>Oluşturucular

[Dosya girişi](#file-input)

### <a name="functions"></a>İşlevler

[Yol](#path)
[türü](#type)

## <a name="file-input"></a>Dosya girişi

```cpp
FileInput(const RawEvent& event);
```

### <a name="parameters"></a>Parametreler

*olay*\
[FILE_INPUT](../event-table.md#file-input) bir olay.

## <a name="path"></a>Yolun

```cpp
const wchar_t Path() const;
```

### <a name="return-value"></a>Dönüş Değeri

Giriş dosyasının mutlak yolu.

## <a name="type"></a>Türüyle

```cpp
Type Type() const;
```

### <a name="return-value"></a>Dönüş Değeri

Giriş dosyasının türünü tanımlayan bir kod.

::: moniker-end
