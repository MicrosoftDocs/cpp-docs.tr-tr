---
description: 'Daha fazla bilgi edinin: Izlenecek yol: proje derleme (C++)'
title: 'İzlenecek Yol: Proje Derleme (C++)'
ms.date: 04/25/2019
helpviewer_keywords:
- building projects [C++]
- projects [C++], building
- project building [C++]
ms.assetid: d459bc03-88ef-48d0-9f9a-82d17f0b6a4d
ms.openlocfilehash: f606a0ead796916fa41f7669852e67d58ae3b17c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97222547"
---
# <a name="walkthrough-building-a-project-c"></a>İzlenecek Yol: Proje Derleme (C++)

Bu kılavuzda, derleme hatasının ne gibi göründüğünü ve nasıl düzeltileceğini öğrenmek için kodunuzda bir C++ sözdizimi hatası ortaya çıkaracak. Projeyi derlerken, sorunun ne olduğunu ve nerede oluştuğunu gösteren bir hata mesajı görüntülenir.

## <a name="prerequisites"></a>Önkoşullar

- Bu izlenecek yol, C++ dilinin temellerini anladığınızı varsayar.

- Ayrıca [, C++ masaüstü geliştirme Için Visual STUDIO IDE 'Yi kullanma](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md)bölümünde listelenen daha önceki ilgili talimatları tamamlamış olduğunu varsaymaktadır.

### <a name="to-fix-compilation-errors"></a>Derleme hatalarını onarmak için

1. Game. cpp ' de, ifadeye benzer şekilde son satırda noktalı virgülü silin:

   `return 0`

1. Menü **çubuğunda Build**  >  **Build Solution** öğesini seçin.

1. **Hata listesi** penceresindeki bir ileti, projenin oluşturulmasında bir hata olduğunu gösterir. Açıklama, hata iletisine benzer bir şekilde görünür:

   `error C2143: syntax error: missing ';' before '}'`

   Bu hatayla ilgili yardım bilgilerini görüntülemek için **hata listesi** penceresinde vurgulayın ve **F1** tuşunu seçin.

1. Sözdizimi hatasına sahip satırın sonuna noktalı virgülden geri ekleyin:

   `return 0;`

1. Menü **çubuğunda Build**  >  **Build Solution** öğesini seçin.

   **Çıkış** penceresindeki bir ileti projenin başarıyla derlendiğini gösterir.

    ```Output
    1>------ Build started: Project: Game, Configuration: Debug Win32 ------
    1>Game.cpp
    1>Game.vcxproj -> C:\Users\<username>\source\repos\Game\Debug\Game.exe
    ========== Build: 1 succeeded, 0 failed, 0 up-to-date, 0 skipped ==========
    ```

## <a name="next-steps"></a>Sonraki Adımlar

**Önceki:** [Izlenecek yol: projelerle ve çözümlerle çalışma (C++)](../ide/walkthrough-working-with-projects-and-solutions-cpp.md)<br/>
**İleri:** [Izlenecek yol: projeyi test etme (C++)](../ide/walkthrough-testing-a-project-cpp.md)

## <a name="see-also"></a>Ayrıca bkz.

[C++ dil başvurusu](../cpp/cpp-language-reference.md)<br/>
[Projeler ve derleme sistemleri](../build/projects-and-build-systems-cpp.md)<br/>
