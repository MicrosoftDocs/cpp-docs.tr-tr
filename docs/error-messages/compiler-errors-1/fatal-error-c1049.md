---
title: Önemli hata C1049
description: Derleyici önemli hatası C1049, geçersiz sayısal bağımsız değişken açıklar ve bu sorunu nasıl çözebileceğinizi açıklar.
ms.date: 11/04/2019
f1_keywords:
- C1049
helpviewer_keywords:
- C1049
ms.openlocfilehash: 9b3cbe5d081e32680e5408fc4a6ddcd932db77a2
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2020
ms.locfileid: "91503265"
---
# <a name="fatal-error-c1049"></a>Önemli hata C1049

> geçersiz sayısal bağımsız değişken '*Value*'

CL.EXE komut satırı ayrıştırıcısı, sayısal bir bağımsız değişken beklediği *değeri* buldu.

Derleyici bu derleyici seçeneklerinden biri için sayısal bir bağımsız değişken bulamadığında bir C1049 hatası oluşabilir:

[/constexpr: derinlik](../../build/reference/constexpr-control-constexpr-evaluation.md)\
[/constexpr: backtrace](../../build/reference/constexpr-control-constexpr-evaluation.md)\
[/constexpr: adımlar](../../build/reference/constexpr-control-constexpr-evaluation.md)

Sayısal bir bağımsız değişken bekleyen komut satırı derleyici seçenekleri,,,, `Command line error D8004` veya rapor edebilir `Command line error D8021` `Command line warning D9002` `Command line warning D9014` `Command line warning D9024` .

Bu hatayı çözmek için, yanlış yerleştirilmiş veya eksik bağımsız değişkenler için komut satırını inceleyin. Seçenekler ve bağımsız değişkenler arasında beklenmeyen bir boşluk olmadığını doğrulayın. Son komut satırı, makrolar, ortam değişkenleri veya diğer derleme sistemi işlemleri tarafından oluşturulabilir. Bu nedenle derleyiciye geçirilen gerçek komut satırına bakmak önemlidir.

- Komut dosyaları veya makefiles 'ta, gerçek komut satırını raporlamak için bir **echo** komutu kullanabilirsiniz.

- Visual Studio 'da projenizin **Özellik sayfaları** iletişim kutusunu açın. **Yapılandırma özellikleri**  >  **C/C++**  >  **genel** sayfasında, **başlangıç başlığını gösterme** özelliğini **Hayır**olarak değiştirin. Değişikliklerinizi kaydetmek için **Tamam ' ı** seçin. **Çıkış** penceresinde artık derleme sırasında komut satırı görüntülenir, telif hakkı satırı hemen sonra.

Diğer derleme sistemleri, kullanılan gerçek komutları görmek için günlük dosyalarına veya ayrıntılı seçeneklere sahip olabilir. Bilgi için, yapı sistemi belgelerinize bakın.
