---
title: 'Nasıl yapılır: yayın derlemesinde hata ayıklama | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- debugging [C++], release builds
- release builds, debugging
ms.assetid: d333e4d1-4e6c-4384-84a9-cb549702da25
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2dcafe151edf907521c2db49b4ffacca38593e9b
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45723911"
---
# <a name="how-to-debug-a-release-build"></a>Nasıl yapılır: Yayın Derlemesinde Hata Ayıklama

Bir uygulamanın bir yayın derlemesinde hata ayıklama.

### <a name="to-debug-a-release-build"></a>Bir yayın derlemesinde hata ayıklama için

1. Açık **özellik sayfaları** iletişim kutusu için proje. Ayrıntılar için bkz [Working with Project Properties](../../ide/working-with-project-properties.md).

1. Tıklayın **C/C++** düğümü. Ayarlama **hata ayıklama bilgi biçimi** için [C7 uyumlu (/ Z7)](../../build/reference/z7-zi-zi-debug-information-format.md) veya **Program veritabanı (/Zi)**.

1. Genişletin **bağlayıcı** tıklatıp **genel** düğümü. Ayarlama **artımlı bağlamayı etkinleştir** için [Hayır (/ INCREMENTAL: NO)](../../build/reference/incremental-link-incrementally.md).

1. Seçin **hata ayıklama** düğümü. Ayarlama **hata ayıklama bilgileri üret** için [Evet (/ DEBUG)](../../build/reference/debug-generate-debug-info.md).

1. Seçin **iyileştirme** düğümü. Ayarlama **başvuruları** için [/OPT: ref](../../build/reference/opt-optimizations.md) ve **COMDAT katlamasını etkinleştir** için [/OPT: ICF](../../build/reference/opt-optimizations.md).

1. Yayın derleme uygulamanız şimdi ayıklayabilirsiniz. Hatanın oluştuğu bulana kadar bir sorun, Adımlama, kodu (veya kullanım Just-ın-Time hata ayıklama) bulun ve sonra yanlış parametreler veya kod belirlemek için.

   Bir uygulama için hata ayıklama çalışır, ancak bu bir yayın derleme başarısız olduğunda, bir derleyici iyileştirmelerini kaynak kodunda bir hata gösterme. Dosya ve soruna neden olan en iyi duruma getirme belirleyene kadar sorunu ayırt etmek için her kaynak kodu dosyası için seçili iyileştirmeleri devre dışı bırakın. (İşlemi hızlandırmak için dosyaları iki gruba ayırın, bir grup iyileştirmesini devre dışı bırakmak ve bir grup içinde bir sorun bulduğunuzda sorun dosya yalıtana kadar bölme devam.)

   Kullanabileceğiniz [/RTC](../../build/reference/rtc-run-time-error-checks.md) hata ayıklama yapılarınızda bu tür hatalar ortaya dener.

   Daha fazla bilgi için [kodunuzu en iyi duruma getirme](../../build/reference/optimizing-your-code.md).

## <a name="see-also"></a>Ayrıca Bkz.

[Yayın Derlemesi Sorunlarını Giderme](../../build/reference/fixing-release-build-problems.md)