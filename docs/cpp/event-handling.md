---
title: Olay İşleme
ms.date: 05/07/2019
helpviewer_keywords:
- event handling [C++]
ms.assetid: 82de3f9a-2d88-470c-9527-8a5b54c8ced4
ms.openlocfilehash: cf16ea0e6e14981f1105456a5f17d68c05a9c3fa
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80189214"
---
# <a name="event-handling"></a>Olay İşleme

Olay işleme öncelikle COM sınıfları (C++ genellikle atl sınıfları veya [COCLASS](../windows/coclass.md) özniteliği kullanarak com nesneleri uygulayan sınıflar) için desteklenir. Daha fazla bilgi için bkz. [com 'Da olay işleme](../cpp/event-handling-in-com.md).

Olay işleme, yerel C++ SıNıFLAR (C++ com nesneleri uygulamayan sınıflar) için de desteklenir, ancak bu destek kullanım dışıdır ve gelecek sürümlerde kaldırılır.  Daha fazla bilgi için bkz. [yerel C++olarak olay işleme ](../cpp/event-handling-in-native-cpp.md).

Olay işleme tek ve çok iş parçacıklı kullanımı destekler ve eşzamanlı çoklu iş parçacığı erişiminizden verileri korur. Ayrıca, olay kaynağı veya alıcı sınıflarından alt sınıfları türetebilir ve türetilmiş sınıfta genişletilmiş olay kaynağını/almayı destekletmeniz de sağlar.

Microsoft C++ derleyicisi olayları ve olay işleyicilerini bildirmek için öznitelikler ve anahtar sözcükler içerir. Olay öznitelikleri ve anahtar sözcükler, CLR programlarında ve yerel C++ programlarda kullanılabilir.

|Konu|Açıklama|
|-----------|-----------------|
|[event_source](../windows/attributes/event-source.md)|Bir olay kaynağı oluşturur.|
|[event_receiver](../windows/attributes/event-receiver.md)|Bir olay alıcısı (havuz) oluşturur.|
|[__event](../cpp/event.md)|Bir olayı bildirir.|
|[__raise](../cpp/raise.md)|Bir olayın çağrı sitesini vurgular.|
|[__hook](../cpp/hook.md)|Bir işleyici yöntemini bir olayla ilişkilendirir.|
|[__unhook](../cpp/unhook.md)|Bir olaydan bir işleyici yönteminin ilişkilendirmesini kaldırın.|

## <a name="see-also"></a>Ayrıca bkz.

[C++ Dil Başvurusu](../cpp/cpp-language-reference.md)<br/>
[Anahtar Sözcükler](../cpp/keywords-cpp.md)
