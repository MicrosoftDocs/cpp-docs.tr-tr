---
title: "-volatile (volatile anahtar sözcük yorumu) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4528d53da01ae83f179f07ba52b2c86c335e883c
ms.sourcegitcommit: 30ab99c775d99371ed22d1a46598e542012ed8c6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/03/2018
---
# <a name="volatile-volatile-keyword-interpretation"></a>/volatile (volatile Anahtar Sözcük Yorumu)

Belirtir nasıl [volatile](../../cpp/volatile-cpp.md) sözcüktür yorumlanacağını.

## <a name="syntax"></a>Sözdizimi

> **/ volatile:**{**ISO**|**ms**}  

## <a name="arguments"></a>Arguments

**/volatile:iso**  
Katı seçer `volatile` ISO standart C++ dili tarafından tanımlanan şekilde semantiği. Alma/sürüm semantiği geçici erişim sırasında garanti edilmez. Derleyici ARM hedefliyorsa, bu varsayılan yorumu olduğu `volatile`.

**/volatile:ms**  
Microsoft genişletilmiş seçer `volatile` garanti ISO standart C++ dili ötesinde sıralama bellek ekleme semantiği. Alma/sürüm semantiği üzerinde geçici erişim sağlanır. Ancak, bu seçenek de önemli ek yükü ARM ve diğer zayıf bellek sıralama mimarileri eklemeleri donanım bellek engelleri oluşturmak için derleyici zorlar. Derleyici ARM dışında herhangi bir platform hedefliyorsa, bu varsayılan yorumu olduğu `volatile`.

## <a name="remarks"></a>Açıklamalar

Kullanmanız önerilir **/volatile:iso** açık eşitleme temelleri ve iş parçacıkları arasında paylaşılan bellek ile ilgilenirken derleyici iç bilgileri ile birlikte. Daha fazla bilgi için bkz: [volatile](../../cpp/volatile-cpp.md).

Bağlantı noktası var olan kodu veya bir proje ortasında bu seçeneği değiştirmek, uyarı etkinleştirmek yararlı olabilir [C4746](../../error-messages/compiler-warnings/compiler-warning-c4746.md) semantiği fark etkilenir kod konumları tanımlamak için.

Yoktur hiçbir `#pragma` bu seçenek denetim eşdeğerdir.

### <a name="to-set-the-volatile-compiler-option-in-visual-studio"></a>/ Volatile ayarlamak için derleyici seçeneği Visual Studio'da

1. Açık **özellik sayfaları** projesi için iletişim kutusu. Daha fazla bilgi için bkz: [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).

1. Seçin **yapılandırma özellikleri** > **C/C++** > **komut satırı** özellik sayfası.

1. İçinde **ek seçenekler** kutusunda, eklemek **/volatile:iso** veya **/volatile:ms** ve ardından **Tamam** veya **Uygula** yaptığınız değişiklikleri kaydetmek için.

## <a name="see-also"></a>Ayrıca bkz.

[volatile](../../cpp/volatile-cpp.md)  
[Derleyici Seçenekleri](../../build/reference/compiler-options.md)  
[Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)  
