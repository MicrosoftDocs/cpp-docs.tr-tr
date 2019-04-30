---
title: Derleyici Hatası C3610
ms.date: 11/04/2016
f1_keywords:
- C3610
helpviewer_keywords:
- C3610
ms.assetid: 9349a348-9d37-4a00-9eab-481039268d31
ms.openlocfilehash: 9965e6420171b2ea48c8fb7bacc0a5a37ea2f227
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64344605"
---
# <a name="compiler-error-c3610"></a>Derleyici Hatası C3610

'valuetype': değer türü olmalıdır 'boxed' yapılmalıdır 'method' yönteminin çağrılabilmesi için önce

Varsayılan olarak, bir değer türü yönetilen yığında değil. .NET çalışma zamanı sınıflardan gibi yöntemleri aramadan önce `Object`, yönetilen yığınla değer türü geçmeniz.

C3610 eski derleyici seçeneği kullanılarak erişilebilir, yalnızca **/clr:oldSyntax**.
