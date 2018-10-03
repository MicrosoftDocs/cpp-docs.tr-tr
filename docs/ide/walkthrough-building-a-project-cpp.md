---
title: 'İzlenecek yol: bir proje derleme (C++) | Microsoft Docs'
ms.custom: ''
ms.date: 09/14/2018
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
ms.openlocfilehash: eca30330e721575443ba9d3f7b0b19c315427eb2
ms.sourcegitcommit: 1d9bd38cacbc783fccd3884b7b92062161c91c84
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/03/2018
ms.locfileid: "48234131"
---
# <a name="walkthrough-building-a-project-c"></a>İzlenecek Yol: Proje Derleme (C++)

Bu kılavuzda, kasıtlı bir derleme hatası nasıl göründüğünü ve nasıl düzeltileceğini öğrenmek için kodunuzda bir Visual C++ sözdizimi hatası tanıtır. Projeyi derlediğinizde, bir hata iletisi sorunun ne olduğunu ve oluştuğu yeri gösterir.

## <a name="prerequisites"></a>Önkoşullar

- Bu izlenecek yol, C++ dili temellerini anladığınızı varsayar.

- Ayrıca, listelenen önceki izlenecek yolları tamamladığınız varsayılır [C++ Masaüstü geliştirmesi için Visual Studio IDE kullanarak](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md).

### <a name="to-fix-compilation-errors"></a>Derleme hatalarını düzeltmek için

1. Deyim benzeyecek şekilde Game.cpp içinde son satırda bulunan noktalı virgülü silin:

    `return 0`

1. Menü çubuğunda, **derleme** > **Çözümü Derle**.

1. Bir ileti **hata listesi** penceresini gösteren projesinin yapı içinde bir hata oluştu. Açıklama hata iletisi şuna benzer:

    `error C2143: syntax error: missing ';' before '}'`

  Bu hatayla ilgili Yardım bilgilerini görüntülemek için onu vurgulayın **hata listesi** penceresi seçip **F1** anahtarı.

1. Geri söz dizimi hatası olan satırın sonuna noktalı virgül ekleyin:

     `return 0;`

1. Menü çubuğunda, **derleme** > **Çözümü Derle**.

  Bir ileti **çıkış** penceresi projenin başarıyla derlendiğini gösterir.

    ```Output
    1>------ Build started: Project: Game, Configuration: Debug Win32 ------
    1>Game.cpp
    1>Game.vcxproj -> C:\Users\<username>\source\repos\Game\Debug\Game.exe
    ========== Build: 1 succeeded, 0 failed, 0 up-to-date, 0 skipped ==========
    ```

## <a name="next-steps"></a>Sonraki Adımlar

**Önceki:** [izlenecek yol: projelerle ve çözümlerle (C++) ile çalışma](../ide/walkthrough-working-with-projects-and-solutions-cpp.md)<br/>
**Sonraki:** [izlenecek yol: projeyi (C++) test etme](../ide/walkthrough-testing-a-project-cpp.md)<br/>

## <a name="see-also"></a>Ayrıca Bkz.

[C++ Dil Başvurusu](../cpp/cpp-language-reference.md)<br/>
[C/C++ Programları Oluşturma](../build/building-c-cpp-programs.md)<br/>
