---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3610'
title: Derleyici hatası C3610
ms.date: 11/04/2016
f1_keywords:
- C3610
helpviewer_keywords:
- C3610
ms.assetid: 9349a348-9d37-4a00-9eab-481039268d31
ms.openlocfilehash: 0fca8f57fcdf2e935620118092708ba1c94f5ec0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97223145"
---
# <a name="compiler-error-c3610"></a>Derleyici hatası C3610

' ValueType ': ' Method ' yönteminin çağrılabilmesi için önce değer türünün ' kutulanmış ' olması gerekir

Varsayılan olarak, bir değer türü yönetilen yığında değildir. .NET çalışma zamanı sınıflarından Yöntemleri (gibi) çağırabilmeniz için önce `Object` değer türünü yönetilen yığına taşımanız gerekir.

C3610 yalnızca eski derleyici seçeneği **/clr: oldSyntax** kullanılarak erişilebilir.
