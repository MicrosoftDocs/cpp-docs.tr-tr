---
title: marshal_context::marshal_context | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- msclr::interop::marshal_context::marshal_context
- marshal_context::marshal_context
- msclr.interop.marshal_context.marshal_context
- marshal_context.marshal_context
dev_langs:
- C++
helpviewer_keywords:
- marshal_context class [C++], operations
ms.assetid: 5f08c895-60b0-4f72-97ff-7ae37c68e853
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 02f238a8d9b9d484073794b9a75888325d95107b
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46399450"
---
# <a name="marshalcontextmarshalcontext"></a>marshal_context::marshal_context

Oluşturur bir `marshal_context` yönetilen ve yerel veri türleri arasında veri dönüştürme için kullanılacak nesne.

## <a name="syntax"></a>Sözdizimi

```
marshal_context();
```

## <a name="remarks"></a>Açıklamalar

Bazı veri dönüştürme bir sıralama bağlamda gerektirir. Bkz: [Overview of Marshaling c++](../dotnet/overview-of-marshaling-in-cpp.md) hangi çevirileri bir bağlamda gerektirir ve uygulamanıza dahil edilecek hazırlama hangi dosya sahip hakkında daha fazla bilgi.

## <a name="example"></a>Örnek

Örneğin bakın [marshal_context::marshal_as](../dotnet/marshal-context-marshal-as.md).

## <a name="requirements"></a>Gereksinimler

**Üst bilgi dosyası:** \<msclr\marshal.h >, \<msclr\marshal_windows.h >, \<msclr\marshal_cppstd.h >, veya \<msclr\marshal_atl.h >

**Namespace:** msclr::interop

## <a name="see-also"></a>Ayrıca Bkz.

[Overview of Marshaling in C++](../dotnet/overview-of-marshaling-in-cpp.md)<br/>
[marshal_as](../dotnet/marshal-as.md)<br/>
[marshal_context Class](../dotnet/marshal-context-class.md)