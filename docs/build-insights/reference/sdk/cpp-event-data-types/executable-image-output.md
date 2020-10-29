---
title: Executableımageoutput sınıfı
description: C++ derleme öngörüleri SDK Yürütülebilirımageoutput sınıfı başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- ExecutableImageOutput
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: bf6bb9790dabc39d1ed6baa417d5dc3bf72ed5e6
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920729"
---
# <a name="executableimageoutput-class"></a>Executableımageoutput sınıfı

::: moniker range="<=msvc-140"

C++ Build Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio **Sürüm** Seçicisi denetimini visual Studio 2017 veya visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=msvc-150"

`ExecutableImageOutput`Sınıfı, [matchevent](../functions/match-event.md), [matcheventınmemberfunction](../functions/match-event-in-member-function.md), [Matcheventstack](../functions/match-event-stack.md)ve [matcheventstackinmemberfunction](../functions/match-event-stack-in-member-function.md) işlevleriyle birlikte kullanılır. [EXECUTABLE_IMAGE_OUTPUT](../event-table.md#executable-image-output) bir olayla eşleştirmek için kullanın.

## <a name="syntax"></a>Syntax

```cpp
class ExecutableImageOutput : public FileOutput
{
public:
    ExecutableImageOutput(const RawEvent& event);
};
```

## <a name="members"></a>Üyeler

[Dosya çıkışı](file-output.md) temel sınıfından devralınan üyelerle birlikte, `ExecutableImageOutput` sınıfı aşağıdaki üyeleri içerir:

### <a name="constructors"></a>Oluşturucular

[ExecutableImageOutput](#executable-image-output)

## <a name="executableimageoutput"></a><a name="executable-image-output"></a> Executableımageoutput

```cpp
ExecutableImageOutput(const RawEvent& event);
```

### <a name="parameters"></a>Parametreler

*olay*\
[EXECUTABLE_IMAGE_OUTPUT](../event-table.md#executable-image-output) bir olay.

::: moniker-end
