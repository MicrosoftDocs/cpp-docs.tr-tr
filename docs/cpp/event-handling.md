---
title: Olay İşleme
ms.date: 05/07/2019
helpviewer_keywords:
- event handling [C++]
ms.assetid: 82de3f9a-2d88-470c-9527-8a5b54c8ced4
ms.openlocfilehash: 4ed2dd2140176fe302d2b6800a3aa7768d17eedd
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2020
ms.locfileid: "91498908"
---
# <a name="event-handling"></a>Olay İşleme

Olay işleme öncelikle COM sınıfları (genellikle ATL sınıfları veya [coclass](../windows/attributes/coclass.md) ÖZNITELIĞI kullanarak com nesneleri uygulayan C++ sınıfları) için desteklenir. Daha fazla bilgi için bkz. [com 'Da olay işleme](../cpp/event-handling-in-com.md).

Olay işleme, yerel C++ sınıfları (COM nesneleri uygulamayan C++ sınıfları) için de desteklenir, ancak bu destek kullanım dışıdır ve gelecek sürümlerde kaldırılır.  Daha fazla bilgi için bkz. [Yerel C++ ' da olay işleme](../cpp/event-handling-in-native-cpp.md).

Olay işleme tek ve çok iş parçacıklı kullanımı destekler ve eşzamanlı çoklu iş parçacığı erişiminizden verileri korur. Ayrıca, olay kaynağı veya alıcı sınıflarından alt sınıfları türetebilir ve türetilmiş sınıfta genişletilmiş olay kaynağını/almayı destekletmeniz de sağlar.

Microsoft C++ derleyicisi olayları ve olay işleyicilerini bildirmek için öznitelikler ve anahtar sözcükler içerir. Olay öznitelikleri ve anahtar sözcükler, CLR programlarında ve yerel C++ programlarında kullanılabilir.

|Konu|Açıklama|
|-----------|-----------------|
|[event_source](../windows/attributes/event-source.md)|Bir olay kaynağı oluşturur.|
|[event_receiver](../windows/attributes/event-receiver.md)|Bir olay alıcısı (havuz) oluşturur.|
|[__event](../cpp/event.md)|Bir olayı bildirir.|
|[__raise](../cpp/raise.md)|Bir olayın çağrı sitesini vurgular.|
|[__hook](../cpp/hook.md)|Bir işleyici yöntemini bir olayla ilişkilendirir.|
|[__unhook](../cpp/unhook.md)|Bir olaydan bir işleyici yönteminin ilişkilendirmesini kaldırın.|

## <a name="see-also"></a>Ayrıca bkz.

[C++ dil başvurusu](../cpp/cpp-language-reference.md)<br/>
[Anahtar sözcükler](../cpp/keywords-cpp.md)
