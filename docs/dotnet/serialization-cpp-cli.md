---
description: 'Daha fazla bilgi edinin: serileştirme (C++/CLı)'
title: Seri Hale Getirme (C++/CLI)
ms.date: 11/04/2016
helpviewer_keywords:
- serialization [C++]
- SerializableAttribute class, managed applications
- NonSerializedAttribute class, managed applications
- managed code [C++], serializing
- .NET Framework [C++], serialization
- serialization [C++], about serialization
ms.assetid: 869010ca-74e1-4989-b409-4643cdb94084
ms.openlocfilehash: 1524ed5d4a000d2006f6f830b1d82119d170c3b2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97164607"
---
# <a name="serialization-ccli"></a>Seri Hale Getirme (C++/CLI)

Yönetilen sınıfların (tek tek alanlar veya özellikler dahil) yönetilen sınıfların serileştirme (bir nesnenin veya üyenin kalıcı bir ortama depolanması işlemi) <xref:System.SerializableAttribute> ve sınıfları tarafından desteklenir <xref:System.NonSerializedAttribute> .

## <a name="remarks"></a>Açıklamalar

Tüm sınıfı seri hale getirmek için bir yönetilen sınıfa **SerializableAttribute** özel özniteliğini uygulayın veya yönetilen sınıfın parçalarını seri hale getirmek için yalnızca belirli alanlara veya özelliklere uygulayın. Yönetilen bir sınıfın alanlarını veya özelliklerini seri hale getirmeden muaf tutmak için **NonSerializedAttribute** özel özniteliğini kullanın.

## <a name="example"></a>Örnek

### <a name="description"></a>Açıklama

Aşağıdaki örnekte, sınıfı `MyClass` (ve özelliği `m_nCount` ) seri hale getirilebilir olarak işaretlenir. Ancak, `m_nData` özelliği **seri olmayan** özel öznitelik tarafından belirtilen şekilde serileştirilmez:

### <a name="code"></a>Kod

```cpp
// serialization_and_mcpp.cpp
// compile with: /LD /clr
using namespace System;

[ Serializable ]
public ref class MyClass {
public:
   int m_nCount;
private:
   [ NonSerialized ]
   int m_nData;
};
```

### <a name="comments"></a>Yorumlar

Her iki özniteliğe de "kısa ad" (**serileştirilebilir** ve **serileştirilmemiş**) kullanılarak başvurulduğunu unutmayın. Bu, [öznitelikleri uygulama](/dotnet/standard/attributes/applying-attributes)bölümünde daha ayrıntılı olarak açıklanmıştır.

## <a name="see-also"></a>Ayrıca bkz.

[C++/CLI (Visual C++) ile .NET Programlama](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)
