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
- attributes [C++/CLI], about attributes
ms.assetid: 3aff8bfa-a2a3-4fcb-a2c6-1d96a2b4c68d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 589bb690e7ce42d00f1db52dbae8d3509e06f1c3
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/10/2018
ms.locfileid: "44313744"
---
# <a name="purpose-of-attributes"></a>Özniteliklerin Amacı

Öznitelikleri, C++ dil Klasik yapısını bozmadan şu anda mümkün yönde genişletin. Öznitelikleri sağlayıcıları (dinamik olarak dil işlevlerini genişletmek için ayrı DLL'ler) sağlar. Öznitelikleri birincil amacı, bileşen Geliştirici üretkenliği düzeyini artırmak ek olarak, COM bileşenleri geliştirme kolaylaştırmaktır. Öznitelikleri uygulanabilir sınıfları, veri üyeleri veya üye işlevleri gibi neredeyse tüm C++ yapı için. Bu yeni teknoloji tarafından sağlanan avantajların bir Vurgu verilmiştir:

- Tanıdık ve basit bir çağırma kuralı kullanıma sunar.

- Kullanır, makroları, hata ayıklayıcı tarafından tanınan kod eklenir.

- Kolay qname'den türetme sıkıcı uygulama ayrıntılarını olmadan temel sınıflar sağlar.

- IDL kod gerekli birkaç kısa özniteliklere sahip bir COM bileşeni tarafından büyük miktarda değiştirir.

Örneğin, bir basit olay havuzu için genel bir ATL sınıf uygulamak için uygulayabilirsiniz [event_receiver](../windows/event-receiver.md) gibi belirli bir sınıfa öznitelik `CMyReceiver`. `event_receiver` Özniteliği uygun kod nesnesi dosyasına ekler için Visual C++ derleyicisi tarafından derlenen sonra.

```cpp
[event_receiver(com)]
class CMyReceiver
{
   void handler1(int i) { ... }
   void handler2(int i, float j) { ... }
}
```

Ardından ayarlayabilirsiniz `CMyReceiver` yöntemleri `handler1` ve `handler2` olayları işlemek için (iç işlevi kullanarak [__hook](../cpp/hook.md)) kullanarak oluşturabileceğiniz bir olay kaynağından [event_source](../windows/event-source.md).

## <a name="see-also"></a>Ayrıca Bkz.

[Kavramları](../windows/attributed-programming-concepts.md)