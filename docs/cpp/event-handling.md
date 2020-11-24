---
title: Olay işleme
description: Microsoft C++ uzantılarının hem COM hem de yerel olay işlemesini nasıl destekledikleri hakkında bilgi edinin.
ms.date: 11/20/2020
helpviewer_keywords:
- event handling [C++]
ms.openlocfilehash: de8cd6dfac2b83e850ec62ff88e192d1c60e427e
ms.sourcegitcommit: b02c61667ff7f38e7add266d0aabd8463f2dbfa1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/23/2020
ms.locfileid: "95483156"
---
# <a name="event-handling"></a>Olay işleme

Olay işleme öncelikle COM sınıfları (genellikle ATL sınıfları veya [coclass](../windows/attributes/coclass.md) ÖZNITELIĞI kullanarak com nesneleri uygulayan C++ sınıfları) için desteklenir. Daha fazla bilgi için bkz. [com 'Da olay işleme](../cpp/event-handling-in-com.md).

Olay işleme, yerel C++ sınıfları (COM nesneleri uygulamayan C++ sınıfları) için de desteklenir. Yerel C++ olay işleme desteği kullanım dışıdır ve gelecek bir sürümde kaldırılacak. Daha fazla bilgi için bkz. [Yerel C++ ' da olay işleme](../cpp/event-handling-in-native-cpp.md).

> [!NOTE]
> Yerel C++ içindeki olay öznitelikleri standart C++ ile uyumsuzdur. Uyumluluk modunu belirttiğinizde derlenirler [`/permissive-`](../build/reference/permissive-standards-conformance.md) .

Olay işleme hem tek hem çok iş parçacıklı kullanımı destekler. Eşzamanlı çoklu iş parçacıklı erişimden verileri korur. Olay kaynağı veya alıcı sınıflarından alt sınıfları türetebilirsiniz. Bu alt sınıflar genişletilmiş olay kaynağını ve almayı destekler.

Microsoft C++ derleyicisi olayları ve olay işleyicilerini bildirmek için öznitelikler ve anahtar sözcükler içerir. Olay öznitelikleri ve anahtar sözcükler, CLR programlarında ve yerel C++ programlarında kullanılabilir.

| Makale | Description |
|--|--|
| [`event_source`](../windows/attributes/event-source.md) | Bir olay kaynağı oluşturur. |
| [`event_receiver`](../windows/attributes/event-receiver.md) | Bir olay alıcısı (havuz) oluşturur. |
| [`__event`](../cpp/event.md) | Bir olayı bildirir. |
| [`__raise`](../cpp/raise.md) | Bir olayın çağrı sitesini vurgular. |
| [`__hook`](../cpp/hook.md) | Bir işleyici yöntemini bir olayla ilişkilendirir. |
| [`__unhook`](../cpp/unhook.md) | Bir işleyici yönteminin bir olaydan ilişkilendirmesini kaldırır. |

## <a name="see-also"></a>Ayrıca bkz.

[C++ dil başvurusu](../cpp/cpp-language-reference.md)\
[Anahtar sözcükler](../cpp/keywords-cpp.md)
