---
title: Önemli hata C1010
ms.date: 08/19/2019
f1_keywords:
- C1010
helpviewer_keywords:
- C1010
ms.assetid: dfd035f1-a7a2-40bc-bc92-dc4d7f456767
ms.openlocfilehash: 35b0f60f7eb3be887598e7ffaf3e3eae74aefcff
ms.sourcegitcommit: 9d4ffb8e6e0d70520a1e1a77805785878d445b8a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/20/2019
ms.locfileid: "69630795"
---
# <a name="fatal-error-c1010"></a>Önemli hata C1010

önceden derlenmiş üst bilgi aranırken beklenmeyen dosya sonu. Kaynağınıza ' #include Name ' eklemeyi mi unuttunuz?

[/Yu](../../build/reference/yu-use-precompiled-header-file.md) ile belirtilen bir içerme dosyası kaynak dosyasında listelenmiyor.  Bu seçenek, çoğu Visual Studio C++ proje türlerinde varsayılan olarak etkindir ve *pch. h* (Visual Studio 2017 ve önceki sürümlerde*stdadfx. h* ), bu seçenekle belirtilen varsayılan içerme dosyasıdır.

Visual Studio ortamında, bu hatayı çözmek için aşağıdaki yöntemlerden birini kullanın:

- Projenizde önceden derlenmiş üstbilgiler kullanmıyorsanız, kaynak dosyaların önceden derlenmiş üst **bilgi oluştur/kullan** özelliğini **önceden derlenmiş üst bilgileri kullanmadan**ayarlayın. Bu derleyici seçeneğini ayarlamak için şu adımları izleyin:

   1. Projenin Çözüm Gezgini bölmesinde, proje adına sağ tıklayın ve ardından **Özellikler**' e tıklayın.

   1. Sol bölmede **C/C++**  klasörüne tıklayın.

   1. **Ön derlenmiş üstbilgiler** düğümüne tıklayın.

   1. Sağ bölmede, **önceden derlenmiş üst bilgi oluştur/kullan**' a tıklayın ve ardından **önceden derlenmiş üst bilgileri**kullanmayan ' e tıklayın.

- (Varsayılan olarak, stdadfx. h) üst bilgi dosyasını güncel projeden yanlışlıkla sildiğinizden, yeniden adlandırdığınızdan veya çıkardığınızdan emin olun. Ayrıca, bu dosyanın **"stbafx. h" #include**kullanarak kaynak dosyalarınızda diğer koddan önce bulunması gerekir. (Bu üstbilgi dosyası dosya projesi özelliği **aracılığıyla PCH oluştur/kullan** olarak belirtilir)