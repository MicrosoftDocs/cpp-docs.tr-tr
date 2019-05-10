---
title: Önemli hata C1010
ms.date: 11/04/2016
f1_keywords:
- C1010
helpviewer_keywords:
- C1010
ms.assetid: dfd035f1-a7a2-40bc-bc92-dc4d7f456767
ms.openlocfilehash: 204c7ef94d82513338f6635ec9eb22f26fc090a7
ms.sourcegitcommit: 7d64c5f226f925642a25e07498567df8bebb00d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2019
ms.locfileid: "65448026"
---
# <a name="fatal-error-c1010"></a>Önemli hata C1010

Beklenmeyen için önceden derlenmiş üst bilgi arayan sırasında dosya sonu. Eklemeyi mi unuttunuz ' #include ' kaynağınız için?

Belirtilen bir dahil etme dosyasından [/Yu](../../build/reference/yu-use-precompiled-header-file.md) kaynak dosyasında listelenmeyen.  Bu seçenek çoğu Visual Studio varsayılan olarak etkin C++ proje türleri ve "stdafx.h" olan bu seçeneği tarafından belirtilen dosya varsayılan içerir.

Visual Studio ortamında, bu hatayı gidermek için aşağıdaki yöntemlerden birini kullanın:

- Projenizde önceden derlenmiş üst bilgiler kullanmayın verilirse **önceden derlenmiş üst bilgi Oluştur/Kullan** özelliği için kaynak dosyalarının **kullanarak önceden derlenmiş üstbilgi**. Bu derleyici seçeneğini ayarlamak için aşağıdaki adımları izleyin:

   1. Çözüm Gezgini bölmesinde projenin proje adına sağ tıklayın ve ardından **özellikleri**.

   1. Sol bölmede **C/C++** klasör.

   1. Tıklayın **önceden derlenmiş üst bilgiler** düğümü.

   1. Sağ bölmede **önceden derlenmiş üst bilgi Oluştur/Kullan**ve ardından **kullanarak önceden derlenmiş üstbilgi**.

- İstemeden silinmiş, yeniden adlandırılmış veya üst bilgi dosyası kaldırıldı emin olun (varsayılan olarak, stdafx.h) geçerli projeden. Bu dosya ayrıca herhangi bir kod kullanarak kaynak dosyalarında önce eklenmesi gerekir **#include "stdafx.h"**. (Bu başlık dosyasının belirtilen **dosya üzerinden PCH Oluştur/Kullan** proje özelliği)