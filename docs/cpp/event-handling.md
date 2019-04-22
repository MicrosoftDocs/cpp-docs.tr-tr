---
title: Olay İşleme
ms.date: 11/04/2016
helpviewer_keywords:
- attributes [C++], event handling
- intrinsic functions [C++], event handling
- event handling [C++], Visual C++
ms.assetid: 82de3f9a-2d88-470c-9527-8a5b54c8ced4
ms.openlocfilehash: 4c6701f04544b336de97196e8b65f4d0cd4be296
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58769478"
---
# <a name="event-handling"></a>Olay İşleme

Olay işleme, COM sınıfları için öncelikle desteklenir (genellikle ATL sınıfları kullanarak, COM nesneleri uygulayan C++ sınıflar veya [coclass'ı](../windows/coclass.md) özniteliği). Daha fazla bilgi için [com'da olay işleme](../cpp/event-handling-in-com.md).

Olay işleme de yerel C++ sınıfları için (COM nesneleri uygulamayan C++ sınıfları), ancak desteği kullanım dışıdır ve gelecek sürümde kaldırılacak desteklenir.  Daha fazla bilgi için [olay işleme yerel C++'ta](../cpp/event-handling-in-native-cpp.md).

Olay işleme, tek ve birden çok iş parçacıklı kullanım destekler ve aynı anda çoklu iş parçacığı erişimine karşı verileri korur. Ayrıca, alt sınıfların olay kaynağından alabilmesine olanak sağlar veya alıcı sınıfları ve Destek, olay kaynağını belirleme/alma türetilmiş sınıftaki genişletilmiş.

Visual C++ öznitelikleri ve olayları ve olay işleyicileri bildirme anahtar sözcükler içerir. Anahtar sözcükler ve olay öznitelikleri CLR programlarda ve yerel C++ programlarında kullanılabilir.

|Konu|Açıklama|
|-----------|-----------------|
|[event_source](../windows/attributes/event-source.md)|Olay kaynağı oluşturur.|
|[event_receiver](../windows/attributes/event-receiver.md)|Bir olay alıcısı (havuz) oluşturur.|
|[__event](../cpp/event.md)|Bir olayı bildirir.|
|[__raise](../cpp/raise.md)|Bir olayın çağrı sitesini vurgular.|
|[__hook](../cpp/hook.md)|İle bir olay işleyicisi yöntemi ilişkilendirir.|
|[__unhook](../cpp/unhook.md)|Bir olay işleyicisi yöntemi dissociates.|

## <a name="see-also"></a>Ayrıca bkz.

[C++ Dil Başvurusu](../cpp/cpp-language-reference.md)<br/>
[Anahtar Sözcükler](../cpp/keywords-cpp.md)