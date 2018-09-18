---
title: Önemli hata C1010 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1010
dev_langs:
- C++
helpviewer_keywords:
- C1010
ms.assetid: dfd035f1-a7a2-40bc-bc92-dc4d7f456767
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5ae762c15c96ed7c12a20d2070d22cdc556667ac
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46064093"
---
# <a name="fatal-error-c1010"></a>Önemli hata C1010

Beklenmeyen için önceden derlenmiş üst bilgi arayan sırasında dosya sonu. Eklemeyi mi unuttunuz ' #include ' kaynağınız için?

Belirtilen bir dahil etme dosyasından [/Yu](../../build/reference/yu-use-precompiled-header-file.md) kaynak dosyasında listelenmeyen.  Bu seçenek çoğu Visual C++ proje türleri varsayılan olarak etkindir ve "stdafx.h" varsayılan, bu seçeneği tarafından belirtilen dosya dahil edilir.

Visual Studio ortamında, bu hatayı gidermek için aşağıdaki yöntemlerden birini kullanın:

- Projenizde önceden derlenmiş üst bilgiler kullanmayın verilirse **önceden derlenmiş üst bilgi Oluştur/Kullan** özelliği için kaynak dosyalarının **kullanarak önceden derlenmiş üstbilgi**. Bu derleyici seçeneğini ayarlamak için aşağıdaki adımları izleyin:

   1. Çözüm Gezgini bölmesinde projenin proje adına sağ tıklayın ve ardından **özellikleri**.

   1. Sol bölmede **C/C++** klasör.

   1. Tıklayın **önceden derlenmiş üst bilgiler** düğümü.

   1. Sağ bölmede **önceden derlenmiş üst bilgi Oluştur/Kullan**ve ardından **kullanarak önceden derlenmiş üstbilgi**.

- İstemeden silinmiş, yeniden adlandırılmış veya üst bilgi dosyası kaldırıldı emin olun (varsayılan olarak, stdafx.h) geçerli projeden. Bu dosya ayrıca herhangi bir kod kullanarak kaynak dosyalarında önce eklenmesi gerekir **#include "stdafx.h"**. (Bu başlık dosyasının belirtilen **dosya üzerinden PCH Oluştur/Kullan** proje özelliği)