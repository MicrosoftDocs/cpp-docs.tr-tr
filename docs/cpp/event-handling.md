---
title: Olay işleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- attributes [C++], event handling
- intrinsic functions [C++], event handling
- event handling [C++], Visual C++
ms.assetid: 82de3f9a-2d88-470c-9527-8a5b54c8ced4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 09029f3afef0a9a28fdc572b9b7d8685cf76e811
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="event-handling"></a>Olay İşleme
Olay işleme COM sınıfları için öncelikle desteklenen (genellikle ATL sınıfları kullanarak COM nesneleri uygulamak C++ sınıfları veya [coclass](../windows/coclass.md) özniteliği).  Daha fazla bilgi için bkz: [olay işleme COM içinde](../cpp/event-handling-in-com.md).  
  
 Olay işleme da yerel C++ sınıfları için (COM nesneleri kullanılmaz C++ sınıfları), ancak desteği kullanım dışıdır ve gelecek sürümde kaldırılacak desteklenir.  Daha fazla bilgi için bkz: [olay işleme yerel C++'ta](../cpp/event-handling-in-native-cpp.md).  
  
 Olay işleme tek ve birden çok iş parçacıklı kullanım destekler ve veri eşzamanlı çoklu iş parçacığı erişime karşı korur. Ayrıca, olay kaynağından alt sınıfların türetmemize olanak sağlar veya olay kaynak Hizmeti'nden/alma türetilen sınıfta genişletilmiş alıcı sınıfları ve destek.  
  
 Visual C++ öznitelikleri ve olayların ve olay işleyicileri bildirme anahtar sözcükleri içerir. Anahtar sözcükler ve olay öznitelikleri CLR programları ve yerel C++ programları kullanılabilir.  
  
|Konu|Açıklama|  
|-----------|-----------------|  
|[event_source](../windows/event-source.md)|Bir olay kaynağı oluşturur.|  
|[event_receiver](../windows/event-receiver.md)|Bir olay alıcısı (havuz) oluşturur.|  
|[__event](../cpp/event.md)|Bir olayı bildirir.|  
|[__raise](../cpp/raise.md)|Bir olayın çağrı sitesini vurgular.|  
|[__hook](../cpp/hook.md)|Bir işleyici yöntemi bir olay ile ilişkilendirir.|  
|[__unhook](../cpp/unhook.md)|Bir olay işleyicisi yönteminden dissociates.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ Dil Başvurusu](../cpp/cpp-language-reference.md)   
 [Anahtar sözcükler](../cpp/keywords-cpp.md)   
 [Olay işleme örnekleri](http://msdn.microsoft.com/en-us/cc0287d4-f92b-4da5-85fc-a0f186e16424)