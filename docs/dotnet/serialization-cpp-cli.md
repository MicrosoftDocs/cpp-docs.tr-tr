---
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
ms.openlocfilehash: b2dfdcaf1a1f33e89d106d4529ffc9af2d08376b
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/10/2019
ms.locfileid: "74988409"
---
# <a name="serialization-ccli"></a>Seri Hale Getirme (C++/CLI)

Yönetilen sınıfların (bireysel alanlar veya özellikler dahil) yönetilen sınıfların serileştirme (bir nesnenin veya üyenin durumunu kalıcı bir ortama depolama işlemi) <xref:System.SerializableAttribute> ve <xref:System.NonSerializedAttribute> sınıfları tarafından desteklenir.

## <a name="remarks"></a>Açıklamalar

Tüm sınıfı seri hale getirmek için bir yönetilen sınıfa **SerializableAttribute** özel özniteliğini uygulayın veya yönetilen sınıfın parçalarını seri hale getirmek için yalnızca belirli alanlara veya özelliklere uygulayın. Yönetilen bir sınıfın alanlarını veya özelliklerini seri hale getirmeden muaf tutmak için **NonSerializedAttribute** özel özniteliğini kullanın.

## <a name="example"></a>Örnek

### <a name="description"></a>Açıklama

Aşağıdaki örnekte, sınıfı `MyClass` (ve özelliği `m_nCount`) seri hale getirilebilir olarak işaretlenir. Ancak, `m_nData` özelliği **seri olmayan** özel öznitelik tarafından belirtildiği gibi serileştirilmez:

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

### <a name="comments"></a>Açıklamalar

Her iki özniteliğe de "kısa ad" (**serileştirilebilir** ve **serileştirilmemiş**) kullanılarak başvurulduğunu unutmayın. Bu, [öznitelikleri uygulama](/dotnet/standard/attributes/applying-attributes)bölümünde daha ayrıntılı olarak açıklanmıştır.

## <a name="see-also"></a>Ayrıca bkz.

[C++/CLI (Visual C++) ile .NET Programlama](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)
