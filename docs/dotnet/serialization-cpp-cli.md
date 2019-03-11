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
ms.openlocfilehash: 794a71ae9a146b691ba6a4377a7fdf2c3ddd3501
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57741396"
---
# <a name="serialization-ccli"></a>Seri Hale Getirme (C++/CLI)

Seri hale getirme (bir nesne veya üye kalıcı bir ortamda durumunu depolama işlemi) tarafından yönetilen sınıflar (bireysel alanlar ve özellikler dahil) desteklenen <xref:System.SerializableAttribute> ve <xref:System.NonSerializedAttribute> sınıfları.

## <a name="remarks"></a>Açıklamalar

Uygulama **SerializableAttribute** sınıfın tamamı seri hale getirmek ya da yalnızca belirli alanlar veya yönetilen sınıf bölümlerini serileştirmek için özellikleri uygulamak için bir yönetilen sınıf özel öznitelik. Kullanım **NonSerializedAttribute** muaf alanlara veya yönetilen bir sınıf özelliklerini serileştirilen öğesinden özel öznitelik.

## <a name="example"></a>Örnek

### <a name="description"></a>Açıklama

Aşağıdaki örnekte, sınıf `MyClass` (ve özellik `m_nCount`) seri hale getirilebilir olarak işaretlenir. Ancak, `m_nData` özelliği tarafından belirtildiği şekilde sıralanmış değildir **getirilmemiş** özel öznitelik:

### <a name="code"></a>Kod

```
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

Her iki öznitelik, "kısa" adıyla başvurulabilir unutmayın (**Serializable** ve **getirilmemiş**). Bu daha ayrıntılı olarak açıklanmıştır [öznitelikleri uygulama](/dotnet/standard/attributes/applying-attributes).

## <a name="see-also"></a>Ayrıca bkz.

[C++/CLI (Visual C++) ile .NET Programlama](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)
