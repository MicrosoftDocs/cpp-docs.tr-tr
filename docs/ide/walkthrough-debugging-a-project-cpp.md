---
title: 'İzlenecek yol: Bir projenin (C++)'
ms.date: 09/14/2018
helpviewer_keywords:
- projects [C++], debugging
- project debugging [C++]
- debugging projects
ms.assetid: a5cade77-ba51-4b03-a7a0-6897e3cd6a59
ms.openlocfilehash: 0a1ceddca3234ead7d10cc839d41a6d644ec1866
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57812037"
---
# <a name="walkthrough-debugging-a-project-c"></a>İzlenecek yol: Bir projenin (C++)

Bu izlenecek yolda, proje sınandığında bulunan sorunu gidermek için programı değiştirin.

## <a name="prerequisites"></a>Önkoşullar

- Bu izlenecek yol, C++ dili temellerini anladığınızı varsayar.

- Ayrıca, listelenen önceki izlenecek yolları tamamladığınız varsayılır [C++ Masaüstü geliştirmesi için Visual Studio IDE kullanarak](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md).

### <a name="to-fix-a-program-that-has-a-bug"></a>Bir hata olan bir program düzeltmek için

1. Ne olacağını görmek için bir `Cardgame` nesnesi yok edildiğinde, yok Edicisi görüntüleme `Cardgame` sınıfı.

   Menü çubuğunda, **görünümü** > **sınıf görünümü**.

   İçinde **sınıf görünümü** penceresinde genişletin **Game** proje ağacı ve seçin **Cardgame** yöntemleri ve sınıf üyeleri görüntülemek için sınıf.

   Kısayol menüsünü açın **~Cardgame(void)** yıkıcı ve ardından **tanıma**.

1. Azaltmak için `totalParticipants` bir Cardgame sona erdiğinde, açılış ve kapanış küme ayraçlarını arasına aşağıdaki kodu ekleyin `Cardgame::~Cardgame` yıkıcı.

   [!code-cpp[NVC_Walkthrough_Debugging_A_Project#110](../ide/codesnippet/CPP/walkthrough-debugging-a-project-cpp_1.cpp)]

1. Siz değiştirdikten sonra aşağıdaki kodu Cardgame.cpp dosya benzemelidir:

   [!code-cpp[NVC_Walkthrough_Debugging_A_Project#111](../ide/codesnippet/CPP/walkthrough-debugging-a-project-cpp_2.cpp)]

1. Menü çubuğunda, **derleme** > **Çözümü Derle**.

1. Derleme tamamlandığında, çalıştırma, hata ayıklama modunda seçerek **hata ayıklama** > **hata ayıklamayı Başlat** seçerek veya menü çubuğunda **F5** anahtarı. Program ilk kesme noktasında duraklatılır.

1. Menü çubuğunda, program aracılığıyla adım tercih **hata ayıklama** > **Step Over**, ya da seçin **F10** anahtarı.

   Her birinden sonra dikkat `Cardgame` Oluşturucusu yürütülmeden, değerini `totalParticipants` artırır. Zaman `PlayGames` işlevi tarafından döndürülen her `Cardgame` örneği kapsam dışına gider ve silindi (ve yok Edicisi çağrılır) `totalParticipants` azaltır. Hemen önce `return` deyimi yürütüldüğünde, `totalParticipants` 0 değerine eşittir.

1. Çıkana kadar adımlarken devam veya seçerek çalışmasına izin **hata ayıklama** > **çalıştırma** seçerek veya menü çubuğunda **F5** anahtarı.

## <a name="next-steps"></a>Sonraki Adımlar

**Önceki:** [İzlenecek yol: Projeyi Test Etme (C++)](../ide/walkthrough-testing-a-project-cpp.md)<br/>
**Sonraki:** [İzlenecek yol: Programınızı Dağıtma (C++)](../ide/walkthrough-deploying-your-program-cpp.md)<br/>

## <a name="see-also"></a>Ayrıca bkz.

[C++ Dil Başvurusu](../cpp/cpp-language-reference.md)<br/>
[Projeler ve yapı sistemi](../build/projects-and-build-systems-cpp.md)<br/>
