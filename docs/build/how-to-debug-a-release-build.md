---
title: 'Nasıl yapılır: Bir yayın derlemesinde hata ayıklama'
ms.date: 11/04/2016
helpviewer_keywords:
- debugging [C++], release builds
- release builds, debugging
ms.assetid: d333e4d1-4e6c-4384-84a9-cb549702da25
ms.openlocfilehash: 6d93fac4e980085c322acb55e6f8758e6cea0a00
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57824154"
---
# <a name="how-to-debug-a-release-build"></a>Nasıl yapılır: Bir yayın derlemesinde hata ayıklama

Bir uygulamanın bir yayın derlemesinde hata ayıklama.

### <a name="to-debug-a-release-build"></a>Bir yayın derlemesinde hata ayıklama için

1. Açık **özellik sayfaları** iletişim kutusu için proje. Ayrıntılar için bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](working-with-project-properties.md).

1. Tıklayın **C/C++** düğümü. Ayarlama **hata ayıklama bilgi biçimi** için [C7 uyumlu (/ Z7)](reference/z7-zi-zi-debug-information-format.md) veya **Program veritabanı (/Zi)**.

1. Genişletin **bağlayıcı** tıklatıp **genel** düğümü. Ayarlama **artımlı bağlamayı etkinleştir** için [Hayır (/ INCREMENTAL: NO)](reference/incremental-link-incrementally.md).

1. Seçin **hata ayıklama** düğümü. Ayarlama **hata ayıklama bilgileri üret** için [Evet (/ DEBUG)](reference/debug-generate-debug-info.md).

1. Seçin **iyileştirme** düğümü. Ayarlama **başvuruları** için [/OPT: ref](reference/opt-optimizations.md) ve **COMDAT katlamasını etkinleştir** için [/OPT: ICF](reference/opt-optimizations.md).

1. Yayın derleme uygulamanız şimdi ayıklayabilirsiniz. Hatanın oluştuğu bulana kadar bir sorun, Adımlama, kodu (veya kullanım Just-ın-Time hata ayıklama) bulun ve sonra yanlış parametreler veya kod belirlemek için.

   Bir uygulama için hata ayıklama çalışır, ancak bu bir yayın derleme başarısız olduğunda, bir derleyici iyileştirmelerini kaynak kodunda bir hata gösterme. Dosya ve soruna neden olan en iyi duruma getirme belirleyene kadar sorunu ayırt etmek için her kaynak kodu dosyası için seçili iyileştirmeleri devre dışı bırakın. (İşlemi hızlandırmak için dosyaları iki gruba ayırın, bir grup iyileştirmesini devre dışı bırakmak ve bir grup içinde bir sorun bulduğunuzda sorun dosya yalıtana kadar bölme devam.)

   Kullanabileceğiniz [/RTC](reference/rtc-run-time-error-checks.md) hata ayıklama yapılarınızda bu tür hatalar ortaya dener.

   Daha fazla bilgi için [kodunuzu en iyi duruma getirme](optimizing-your-code.md).

## <a name="see-also"></a>Ayrıca bkz.

[Yayın Derlemesi Sorunlarını Giderme](fixing-release-build-problems.md)
