---
title: marshal_context Sınıfı
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- marshal_context
helpviewer_keywords:
- marshal_context class [C++]
ms.assetid: 241b0cf6-4ca4-4812-aaee-d671c11dc034
ms.openlocfilehash: 0e25aee0996b0cd16ca92566da22d377b762d7bc
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50594538"
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