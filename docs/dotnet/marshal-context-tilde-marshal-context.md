---
title: marshal_context::~marshal_context
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- marshal_context::~marshal_context
- msclr.interop.marshal_context.~marshal_context
- marshal_context.~marshal_context
- msclr::interop::marshal_context::~marshal_context
- ~marshal_context
helpviewer_keywords:
- marshal_context class [C++], operations
ms.assetid: 34c41b38-4c33-4f61-b74e-831ac46b4ab5
ms.openlocfilehash: 3bf16ab2dde4047fb845cd700821d097f733a4d2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50528225"
---
# <a name="marshalcontextmarshalcontext"></a>marshal_context::~marshal_context

Yok eder bir `marshal_context` nesne.

## <a name="syntax"></a>Sözdizimi

```
~marshal_context();
```

## <a name="remarks"></a>Açıklamalar

Bazı veri dönüştürme bir sıralama bağlamda gerektirir. Bkz: [Overview of Marshaling c++](../dotnet/overview-of-marshaling-in-cpp.md) hangi çevirileri bir bağlamda gerektirir ve uygulamanıza dahil edilecek hazırlama hangi dosya sahip hakkında daha fazla bilgi.

Silme bir `marshal_context` söz konusu bağlamdan dönüştürülen bir veri nesnesi geçersiz kılacak. Sonra verilerinizi korumak istiyorsanız bir `marshal_context` nesnesi yok edildiğinde, veriler korunur bir değişkene elle kopyalamanız gerekir.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi dosyası:** \<msclr\marshal.h >, \<msclr\marshal_windows.h >, \<msclr\marshal_cppstd.h >, veya \<msclr\marshal_atl.h >

**Namespace:** msclr::interop

## <a name="see-also"></a>Ayrıca Bkz.

[Overview of Marshaling in C++](../dotnet/overview-of-marshaling-in-cpp.md)<br/>
[marshal_as](../dotnet/marshal-as.md)<br/>
[marshal_context Class](../dotnet/marshal-context-class.md)