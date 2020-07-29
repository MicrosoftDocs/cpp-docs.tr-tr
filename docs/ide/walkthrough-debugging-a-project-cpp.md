---
title: 'İzlenecek Yol: Proje Hatalarını Ayıklama (C++)'
ms.date: 04/25/2019
helpviewer_keywords:
- projects [C++], debugging
- project debugging [C++]
- debugging projects
ms.assetid: a5cade77-ba51-4b03-a7a0-6897e3cd6a59
ms.openlocfilehash: 61433213619c16caf67de905a6da93c7360db298
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87219683"
---
# <a name="walkthrough-debugging-a-project-c"></a>İzlenecek Yol: Proje Hatalarını Ayıklama (C++)

Bu kılavuzda, projeyi test ettiğinizde bulduğunuz sorunu gidermek için programı değiştirirsiniz.

## <a name="prerequisites"></a>Önkoşullar

- Bu izlenecek yol, C++ dilinin temellerini anladığınızı varsayar.

- Ayrıca [, C++ masaüstü geliştirme Için Visual STUDIO IDE 'Yi kullanma](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md)bölümünde listelenen daha önceki ilgili talimatları tamamlamış olduğunu varsaymaktadır.

### <a name="to-fix-a-program-that-has-a-bug"></a>Hata içeren bir programı onarmak için

1. Bir nesne yok edildiğinde ne olduğunu görmek için `Cardgame` , sınıf için yıkıcıyı görüntüleyin `Cardgame` .

   Menü çubuğunda sınıf görünümü **görüntüle**' yi seçin  >  **Class View**.

   **Sınıf görünümü** penceresinde, **oyun** projesi ağacını genişletin ve sınıf üyelerini ve yöntemlerini göstermek için **Cardgame** sınıfını seçin.

   **~ Cardgame (void)** yıkıcısı için kısayol menüsünü açın ve ardından **Tanıma Git**' i seçin.

1. `totalParticipants`Bir Cardgame 'in ne zaman sona ereceğini azaltmak için, yok edicinin açılış ve kapanış ayraçları arasına aşağıdaki kodu ekleyin `Cardgame::~Cardgame` .

   [!code-cpp[NVC_Walkthrough_Debugging_A_Project#110](../ide/codesnippet/CPP/walkthrough-debugging-a-project-cpp_1.cpp)]

1. Cardgame. cpp dosyası, değiştirdikten sonra aşağıdaki koda benzemelidir:

   [!code-cpp[NVC_Walkthrough_Debugging_A_Project#111](../ide/codesnippet/CPP/walkthrough-debugging-a-project-cpp_2.cpp)]

1. Menü **çubuğunda Build**  >  **Build Solution**öğesini seçin.

1. Oluşturma tamamlandığında, menü çubuğunda Hata **Ayıkla**  >  **Başlat** ' ı seçerek veya **F5** tuşunu seçerek bunu hata ayıklama modunda çalıştırın. Program ilk kesme noktasında duraklatılır.

1. Programda ilerlemek için, menü çubuğunda **Hata Ayıkla**  >  **adımlayın**' i seçin veya **F10** tuşunu seçin.

   Her bir `Cardgame` Oluşturucu yürütüldükten sonra, artış değeri olduğuna dikkat edin `totalParticipants` . İşlev döndürüldüğünde `PlayGames` , her `Cardgame` örnek kapsam dışına çıkar ve silinir (ve yıkıcı çağrıldığında), `totalParticipants` azalır. **`return`** Deyimden hemen önce, 0 ' a `totalParticipants` eşittir.

1. Programdan çıkana kadar devam edin veya menü çubuğunda **Hata Ayıkla**  >  **Çalıştır** ' ı seçerek veya **F5** tuşunu seçerek çalışmasına izin verin.

## <a name="next-steps"></a>Sonraki Adımlar

**Previous:** [Izlenecek yol: projeyi test etme (C++)](../ide/walkthrough-testing-a-project-cpp.md)<br/>
**Sonraki:** [Izlenecek yol: programınızı dağıtma (C++)](../ide/walkthrough-deploying-your-program-cpp.md)

## <a name="see-also"></a>Ayrıca bkz.

[C++ dil başvurusu](../cpp/cpp-language-reference.md)<br/>
[Projeler ve derleme sistemleri](../build/projects-and-build-systems-cpp.md)<br/>
