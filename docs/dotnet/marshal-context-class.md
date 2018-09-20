---
title: marshal_context sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- marshal_context
dev_langs:
- C++
helpviewer_keywords:
- marshal_context class [C++]
ms.assetid: 241b0cf6-4ca4-4812-aaee-d671c11dc034
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: fc3399ee088a0430ca857c3e421742ee484d337a
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46413322"
---
# <a name="marshalcontext-class"></a>marshal_context Sınıfı

Bu sınıf, yerel ve yönetilen ortamlar arasında verileri dönüştürür.

## <a name="syntax"></a>Sözdizimi

```
class marshal_context
```

## <a name="remarks"></a>Açıklamalar

Kullanım `marshal_context` sınıfı için bir bağlam gerektiren veri dönüştürme. Bkz: [Overview of Marshaling c++](../dotnet/overview-of-marshaling-in-cpp.md) hangi dönüştürmeler bir bağlamda gerektirir ve hangi hazırlama dosyasını dahil olmak zorundadır hakkında daha fazla bilgi. Bir bağlam kullandığınızda hazırlama sonucu yalnızca kadar geçerli olan `marshal_context` nesnesi yok edildiğinde. Sonuç korumak için verileri kopyalamanız gerekir.

Aynı `marshal_context` birden çok veri dönüştürme için kullanılabilir. Bu şekilde bağlamı yeniden sıralama önceki çağrılarının sonucunu etkilemez.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi dosyası:** \<msclr\marshal.h >, \<msclr\marshal_windows.h >, \<msclr\marshal_cppstd.h >, veya \<msclr\marshal_atl.h >

**Namespace:** msclr::interop

## <a name="see-also"></a>Ayrıca Bkz.

[Overview of Marshaling in C++](../dotnet/overview-of-marshaling-in-cpp.md)<br/>
[marshal_as](../dotnet/marshal-as.md)