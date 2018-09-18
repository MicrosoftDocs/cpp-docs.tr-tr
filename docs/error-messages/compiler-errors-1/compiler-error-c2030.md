---
title: Derleyici Hatası C2030 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2030
dev_langs:
- C++
helpviewer_keywords:
- C2030
ms.assetid: 5806cead-64df-4eff-92de-52c9a3f5ee62
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b0c5849c372cc4c7ebf27dbe010e65d406ad1ab1
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46032908"
---
# <a name="compiler-error-c2030"></a>Derleyici Hatası C2030

erişebilirliği 'protected private' olan bir yok edici 'sealed' olarak bildirilmiş bir sınıfın üyesi olamaz

Bir Windows çalışma zamanı sınıf olarak bildirilen `sealed` özel korumalı bir yok Edicisi olamaz. Yalnızca genel sanal ve özel sanal olmayan yok ediciler sealed türlerde izin verilir. Daha fazla bilgi için [başvuru sınıfları ve yapıları](../../cppcx/ref-classes-and-structs-c-cx.md).

Bu hatayı düzeltmek için yok edici erişilebilirliğini değiştirin.