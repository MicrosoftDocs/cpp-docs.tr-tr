---
title: "Özniteliklerin amacı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: attributes [C++], about attributes
ms.assetid: 3aff8bfa-a2a3-4fcb-a2c6-1d96a2b4c68d
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ed20c29d017527d5c2ce0b0c5ab8053fc75dc6ee
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="purpose-of-attributes"></a>Özniteliklerin Amacı
Öznitelikleri C++ dili Klasik yapısını bozmadan şu anda olası yönde genişletir. Öznitelikleri sağlayıcıları (dinamik olarak dil işlevselliğini genişletmek için ayrı DLL'ler) izin verir. Öznitelikleri birincil amacı, bileşen Geliştirici üretkenliği düzeyini artırma ek olarak, COM bileşenlerini yazma kolaylaştırmaktır. Öznitelikleri uygulanabilir sınıfları, veri üyeleri veya üye işlevleri gibi neredeyse tüm C++ yapı için. Bu yeni teknoloji tarafından sağlanan avantajlarından Vurgu verilmiştir:  
  
-   Tanıdık ve basit bir çağırma kullanıma sunar.  
  
-   Kullanır, makroları farklı olarak, hata ayıklayıcı tarafından tanınan kodu eklenir.  
  
-   Temel sınıflar sıkıcı uygulama ayrıntılarını olmadan kolay türetmeye izin verir.  
  
-   IDL kod birkaç kısa özniteliklere sahip bir COM bileşeni tarafından gereken büyük miktarda yerini alır.  
  
 Örneğin, bir basit olay havuz için genel bir ATL sınıf uygulamak için uygulanabilir [event_receiver](../windows/event-receiver.md) gibi belirli bir sınıfa öznitelik `CMyReceiver`. **Event_receiver** özniteliği uygun kodu nesne dosyasına ekler Visual C++ derleyicisi tarafından derlenen sonra.  
  
```  
[event_receiver(com)]  
class CMyReceiver   
{  
   void handler1(int i) { ... }  
   void handler2(int i, float j) { ... }  
}  
```  
  
 Ardından ayarlayabilirsiniz **CMyReceiver** yöntemleri `handler1` ve `handler2` olayları işlemek için (iç işlevini kullanarak [__hook](../cpp/hook.md)) kullanarakoluşturabileceğinizbirkaynaktanolay[event_source](../windows/event-source.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kavramları](../windows/attributed-programming-concepts.md)