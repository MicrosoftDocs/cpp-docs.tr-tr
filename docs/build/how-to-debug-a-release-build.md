---
title: 'Nasıl yapılır: Yayın Derlemesinde Hata Ayıklama'
ms.date: 11/04/2016
helpviewer_keywords:
- debugging [C++], release builds
- release builds, debugging
ms.assetid: d333e4d1-4e6c-4384-84a9-cb549702da25
ms.openlocfilehash: 6d93fac4e980085c322acb55e6f8758e6cea0a00
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62188970"
---
# <a name="how-to-debug-a-release-build"></a>Nasıl yapılır: Yayın Derlemesinde Hata Ayıklama

Bir uygulamanın yayın derlemesinde hata ayıklaması yapabilirsiniz.

### <a name="to-debug-a-release-build"></a>Bir yayın derlemesinde hata ayıklamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](working-with-project-properties.md).

1. **C/C++** düğümüne tıklayın. **Hata ayıklama bilgileri biçimini** [C7 uyumlu (/Z7)](reference/z7-zi-zi-debug-information-format.md) veya **Program veritabanı (/Zi)** olarak ayarlayın.

1. **Bağlayıcı** ' yı genişletin ve **genel** düğümüne tıklayın. **Artımlı bağlamayı** Hayır olarak ayarlayın [(/artımlı: No)](reference/incremental-link-incrementally.md).

1. **Hata ayıklama** düğümünü seçin. **Hata ayıklama bilgilerini** [Evet (/Debug)](reference/debug-generate-debug-info.md)olarak ayarlayın.

1. **İyileştirme** düğümünü seçin. [/OPT: ref](reference/opt-optimizations.md) **başvurularını** ayarlayın ve **COMDAT KATLAMAYı** [/OPT: ICF](reference/opt-optimizations.md)olarak etkinleştirin.

1. Artık yayın yapı uygulamanızda hata ayıklaması yapabilirsiniz. Bir sorunu bulmak için, hatanın nerede oluştuğunu bulana kadar kodda ilerleyin (veya Just-In-Time hata ayıklamayı kullanın) ve ardından hatalı parametreleri veya kodu saptayın.

   Bir uygulama bir hata ayıklama derlemesinde çalışıyorsa, ancak bir yayın derlemesinde başarısız olursa, derleyici iyileştirmelerinden biri kaynak kodunda bir hata ortaya çıkarmayabilir. Sorunu yalıtmak için, dosyayı ve soruna neden olan en iyi duruma getirmeyi bulana kadar, her kaynak kodu dosyası için seçilen iyileştirmeleri devre dışı bırakın. (İşlemi hızlandırmak için, dosyaları iki gruba bölebilir, tek bir grupta iyileştirmeyi devre dışı bırakabilirsiniz ve bir grupta sorun bulduğunuzda, sorun dosyasını yalıtana kadar bölmeye devam edin.)

   Hata ayıklama derlemelerinizi bu tür hataları ortaya çıkarmak için [/RTC](reference/rtc-run-time-error-checks.md) ' i kullanabilirsiniz.

   Daha fazla bilgi için bkz. [kodunuzu iyileştirme](optimizing-your-code.md).

## <a name="see-also"></a>Ayrıca bkz.

[Yayın Derlemesi Sorunlarını Giderme](fixing-release-build-problems.md)
