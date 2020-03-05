---
title: FileOutput sınıfı
description: C++ BUILD Insights SDK dosyası çıkış sınıfı başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- FileOutput
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 1c4053d0378ddb9d5dd061bbc9889c454dc9b52c
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78333344"
---
# <a name="fileoutput-class"></a>FileOutput sınıfı

::: moniker range="<=vs-2015"

Build C++ Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio sürüm Seçicisi denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın.

::: moniker-end
::: moniker range=">=vs-2017"

`FileOutput` sınıfı [Matchevent](../functions/match-event.md), [matcheventınmemberfunction](../functions/match-event-in-member-function.md), [Matcheventstack](../functions/match-event-stack.md)ve [matcheventstackinmemberfunction](../functions/match-event-stack-in-member-function.md) işlevleriyle birlikte kullanılır. [EXECUTABLE_IMAGE_OUTPUT](../event-table.md#executable-image-output), [EXP_OUTPUT](../event-table.md#exp-output), [IMP_LIB_OUTPUT](../event-table.md#imp-lib-output), [LIB_OUTPUT](../event-table.md#lib-output)veya [OBJ_OUTPUT](../event-table.md#obj-output) olayını eşleştirmek için kullanın.

## <a name="syntax"></a>Sözdizimi

```cpp
class FileOutput : public SimpleEvent
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

    FileOutput(const RawEvent& event);

    const wchar_t* Path() const;
    Type           Type() const;
};
```

## <a name="members"></a>Üyeler

[SimpleEvent](simple-event.md) temel sınıfından devralınan üyelerle birlikte `FileOutput` sınıfı aşağıdaki üyeleri içerir:

### <a name="constructors"></a>Oluşturucular

[Dosya çıkışı](#file-output)

### <a name="functions"></a>İşlevler

[Yol](#path)
[türü](#type)

## <a name="file-output"></a>Dosya çıkışı

```cpp
FileOutput(const RawEvent& event);
```

### <a name="parameters"></a>Parametreler

*olay*\
[EXECUTABLE_IMAGE_OUTPUT](../event-table.md#executable-image-output), [EXP_OUTPUT](../event-table.md#exp-output), [IMP_LIB_OUTPUT](../event-table.md#imp-lib-output), [LIB_OUTPUT](../event-table.md#lib-output)veya [OBJ_OUTPUT](../event-table.md#obj-output) olay.

## <a name="path"></a>Yolun

```cpp
const wchar_t Path() const;
```

### <a name="return-value"></a>Dönüş Değeri

Çıkış dosyasının mutlak yolu.

## <a name="type"></a>Türüyle

```cpp
Type Type() const;
```

### <a name="return-value"></a>Dönüş Değeri

Çıkış dosyasının türünü tanımlayan bir kod.

::: moniker-end
