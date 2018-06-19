---
title: Özniteliklerin amacı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- attributes [C++], about attributes
ms.assetid: 3aff8bfa-a2a3-4fcb-a2c6-1d96a2b4c68d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0ea3b731cc22d144e2e20dc70f14e6b0b76b1479
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33877842"
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