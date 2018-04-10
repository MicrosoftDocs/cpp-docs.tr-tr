---
title: Seri hale getirme (C + +/ CLI) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- serialization [C++]
- SerializableAttribute class, managed applications
- NonSerializedAttribute class, managed applications
- managed code [C++], serializing
- .NET Framework [C++], serialization
- serialization [C++], about serialization
ms.assetid: 869010ca-74e1-4989-b409-4643cdb94084
caps.latest.revision: 13
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 6efd56655cb5b262eab7d7f14c197e11466fb8bf
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="serialization-ccli"></a>Seri Hale Getirme (C++/CLI)
Seri hale getirme (durumunu nesne veya üye kalıcı bir ortamda depolama işlemi) Yönetilen sınıfları (bireysel alanlar ve özellikler dahil) tarafından desteklenen <xref:System.SerializableAttribute> ve <xref:System.NonSerializedAttribute> sınıfları.  
  
## <a name="remarks"></a>Açıklamalar  
 Uygulama **SerializableAttribute** tüm sınıf serileştirmek veya yalnızca belirli alanlar veya yönetilen sınıf bölümlerini serileştirmek için özellikleri uygulamak için bir yönetilen sınıf için özel öznitelik. Kullanım **NonSerializedAttribute** muaf alanlara veya bir yönetilen sınıf özelliklerini özel öznitelik seri hale gelen.  
  
## <a name="example"></a>Örnek  
  
### <a name="description"></a>Açıklama  
 Aşağıdaki örnekte, sınıf `MyClass` (ve özelliği `m_nCount`) seri hale getirilebilir olarak işaretlenmiş. Ancak, `m_nData` özelliği tarafından belirtildiği şekilde sıralanmış değildir **getirilmemiş** özel öznitelik:  
  
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
 Her iki öznitelik kendi "kısa ad" kullanarak başvurulabilir unutmayın (**Serializable** ve **getirilmemiş**). Bu daha ayrıntılı olarak anlatılmıştır [öznitelikleri uygulama](/dotnet/standard/attributes/applying-attributes).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++/CLI (Visual C++) ile .NET Programlama](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)