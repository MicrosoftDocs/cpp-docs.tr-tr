---
title: /volatile (volatile Anahtar Sözcük Yorumu)
ms.date: 11/04/2016
f1_keywords:
- /volatile:iso
- /volatile:ms
- /volatile
helpviewer_keywords:
- /volatile compiler option
- /volatile compiler option [C++]
- -volatile compiler option
- volatile compiler option [C++]
- volatile compiler option
- -volatile compiler option [C++]
ms.assetid: 9d08fcc6-5bda-44c8-8151-8d8d54f164b8
ms.openlocfilehash: 02871622242930d7419fda16f4d106fccb2056f0
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57819499"
---
# <a name="volatile-volatile-keyword-interpretation"></a>/volatile (volatile Anahtar Sözcük Yorumu)

Belirtir nasıl [geçici](../../cpp/volatile-cpp.md) yorumlanacağını sözcüktür.

## <a name="syntax"></a>Sözdizimi

> **/ volatile:**{**ISO**|**ms**}

## <a name="arguments"></a>Arguments

**/volatile:iso**<br/>
Katı seçer `volatile` ISO standardı C++ dili tarafından tanımlanan şekilde semantiği. Acquire/release semantikleri geçici erişimlerde garanti edilmez. Derleyici ARM hedeflerse bu öğesinin varsayılan yorumlamasıdır `volatile`.

**/volatile:MS**<br/>
Microsoft genişletilmiş seçer `volatile` bellek ISO standardındaki C++ dilinin ötesini garanti eder sıralaması eklemesi semantiğini. Acquire/release semantikleri geçici erişimlerde garanti edilir. Ancak, bu seçenek ayrıca derleyicinin önemli ölçüde ARM ve diğer zayıf bellek sıralama mimarilerinin eklemeleri donanım belleği engelleri oluşturmaya zorlar. Derleyici ARM dışında herhangi bir platformu hedeflerse bu öğesinin varsayılan yorumlamasıdır `volatile`.

## <a name="remarks"></a>Açıklamalar

Kullanmanızı öneririz **/volatile:iso** yanı sıra açık eşitleme temel öğeleri ve iş parçacıkları arasında paylaşılan bellek ile uğraşırken derleyici iç bilgileri. Daha fazla bilgi için [geçici](../../cpp/volatile-cpp.md).

Bir projenin ortasında bu seçeneği mevcut koda veya değiştirirseniz uyarısını etkinleştirmek yardımcı olabilecek [C4746](../../error-messages/compiler-warnings/compiler-warning-c4746.md) semantiklerden etkilenen kod konumlarını tanımlamak için.

Var olan hiçbir `#pragma` eşdeğer bu seçimi denetlemek için.

### <a name="to-set-the-volatile-compiler-option-in-visual-studio"></a>Derleyici seçeneğini Visual Studio içinde / volatile belirlemek için

1. Açık **özellik sayfaları** iletişim kutusu için proje. Daha fazla bilgi için [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Seçin **yapılandırma özellikleri** > **C/C++** > **komut satırı** özellik sayfası.

1. İçinde **ek seçenekler** kutusunda **/volatile:iso** veya **/volatile:ms** seçip **Tamam** veya **Uygula** yaptığınız değişiklikleri kaydedin.

## <a name="see-also"></a>Ayrıca bkz.

[volatile](../../cpp/volatile-cpp.md)<br/>
[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici komut satırı sözdizimi](compiler-command-line-syntax.md)
