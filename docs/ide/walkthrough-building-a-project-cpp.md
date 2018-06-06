---
title: 'İzlenecek yol: bir proje derleme (C++) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- building projects [C++]
- projects [C++], building
- project building [C++]
ms.assetid: d459bc03-88ef-48d0-9f9a-82d17f0b6a4d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0c8d04dc3692076b867302af0e793eaac7ed25cb
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "33332461"
---
# <a name="walkthrough-building-a-project-c"></a>İzlenecek Yol: Proje Derleme (C++)
Bu kılavuzda, kasıtlı olarak bir Visual C++ söz dizimi hatası derleme hatası nasıl göründüğünü ve nasıl düzeltileceği öğrenmek için kodunuzda tanıtır. Proje derleme yaparken bir hata iletisi sorunun ne olduğunu ve nerede oluştuğunu gösterir.  
  
## <a name="prerequisites"></a>Önkoşullar  
  
-   Bu kılavuz, C++ dil temelleri anladığınızı varsayar.  
  
-   Ayrıca listelenen ilgili daha önce izlenecek tamamladığınızı varsaymaktadır [C++ Masaüstü geliştirmesi için Visual Studio IDE kullanarak](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md).  
  
### <a name="to-fix-compilation-errors"></a>Derleme hataları gidermek için  
  
1.  Böylece bu benzer TestGames.cpp içinde son satırında noktalı virgülü silin:  
  
     `return 0`  
  
2.  Menü çubuğunda seçin **yapı**, **yapı çözümü**.  
  
3.  Bir ileti **hata listesi** penceresi gösterir proje binada bir hata oluştu. Açıklama şuna benzer:  
  
     `error C2143: syntax error : missing ';' before '}'`  
  
     Bu hatayla ilgili Yardım bilgilerini görüntülemek için de Vurgula **hata listesi** penceresi ve F1 tuşuna'i seçin.  
  
4.  Noktalı virgül geri sözdizimi hatası var. satırın sonuna ekleyin:  
  
     `return 0;`  
  
5.  Menü çubuğunda seçin **yapı**, **yapı çözümü**.  
  
     Bir ileti **çıkış** penceresi gösterir Proje başarıyla derlenir.  
  
    ```Output  
    1>------ Build started: Project: Game, Configuration: Debug Win32 ------  
    1>  TestGames.cpp  
    1>  Game.vcxproj -> C:\Users\<username>\Documents\Visual Studio <version>\Projects\Game\Debug\Game.exe  
    ========== Build: 1 succeeded, 0 failed, 0 up-to-date, 0 skipped ==========  
    ```  
  
## <a name="next-steps"></a>Sonraki Adımlar  
 **Önceki:** [izlenecek yol: projeler ve çözümler (C++) ile çalışma](../ide/walkthrough-working-with-projects-and-solutions-cpp.md) &#124; **sonraki:**[izlenecek yol: Proje (C++) test etme](../ide/walkthrough-testing-a-project-cpp.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ Dil Başvurusu](../cpp/cpp-language-reference.md)   
 [C/C++ Programları Oluşturma](../build/building-c-cpp-programs.md)