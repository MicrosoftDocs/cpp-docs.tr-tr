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
ms.openlocfilehash: 91fded4380875515da81b87c5ffd74665df01b21
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39408033"
---
# <a name="event-handling"></a>Olay İşleme
Olay işleme, COM sınıfları için öncelikle desteklenir (genellikle ATL sınıfları kullanarak, COM nesneleri uygulayan C++ sınıflar veya [coclass'ı](../windows/coclass.md) özniteliği).  Daha fazla bilgi için [com'da olay işleme](../cpp/event-handling-in-com.md).  
  
 Olay işleme de yerel C++ sınıfları için (COM nesneleri uygulamayan C++ sınıfları), ancak desteği kullanım dışıdır ve gelecek sürümde kaldırılacak desteklenir.  Daha fazla bilgi için [olay işleme yerel C++'ta](../cpp/event-handling-in-native-cpp.md).  
  
 Olay işleme, tek ve birden çok iş parçacıklı kullanım destekler ve aynı anda çoklu iş parçacığı erişimine karşı verileri korur. Ayrıca, alt sınıfların olay kaynağından alabilmesine olanak sağlar veya alıcı sınıfları ve Destek, olay kaynağını belirleme/alma türetilmiş sınıftaki genişletilmiş.  
  
 Visual C++ öznitelikleri ve olayları ve olay işleyicileri bildirme anahtar sözcükler içerir. Anahtar sözcükler ve olay öznitelikleri CLR programlarda ve yerel C++ programlarında kullanılabilir.  
  
|Konu|Açıklama|  
|-----------|-----------------|  
|[event_source](../windows/event-source.md)|Olay kaynağı oluşturur.|  
|[event_receiver](../windows/event-receiver.md)|Bir olay alıcısı (havuz) oluşturur.|  
|[__event](../cpp/event.md)|Bir olayı bildirir.|  
|[__raise](../cpp/raise.md)|Bir olayın çağrı sitesini vurgular.|  
|[__hook](../cpp/hook.md)|İle bir olay işleyicisi yöntemi ilişkilendirir.|  
|[__unhook](../cpp/unhook.md)|Bir olay işleyicisi yöntemi dissociates.|  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [C++ Dil Başvurusu](../cpp/cpp-language-reference.md)   
 [Anahtar Sözcükler](../cpp/keywords-cpp.md)   