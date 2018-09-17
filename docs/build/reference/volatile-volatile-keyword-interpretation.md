---
title: -volatile (volatile anahtar sözcük yorumu) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /volatile:iso
- /volatile:ms
- /volatile
dev_langs:
- C++
helpviewer_keywords:
- /volatile compiler option
- /volatile compiler option [C++]
- -volatile compiler option
- volatile compiler option [C++]
- volatile compiler option
- -volatile compiler option [C++]
ms.assetid: 9d08fcc6-5bda-44c8-8151-8d8d54f164b8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4204d602d1390bf30080a800174426513faf0467
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45723640"
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

1. Açık **özellik sayfaları** iletişim kutusu için proje. Daha fazla bilgi için [Working with Project Properties](../../ide/working-with-project-properties.md).

1. Seçin **yapılandırma özellikleri** > **C/C++** > **komut satırı** özellik sayfası.

1. İçinde **ek seçenekler** kutusunda **/volatile:iso** veya **/volatile:ms** seçip **Tamam** veya **Uygula** yaptığınız değişiklikleri kaydedin.

## <a name="see-also"></a>Ayrıca bkz.

[volatile](../../cpp/volatile-cpp.md)<br/>
[Derleyici Seçenekleri](../../build/reference/compiler-options.md)<br/>
[Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)
