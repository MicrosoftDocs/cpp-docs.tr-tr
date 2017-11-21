---
title: "-volatile (volatile anahtar sözcük yorumu) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /volatile:iso
- /volatile:ms
- /volatile
dev_langs: C++
helpviewer_keywords:
- /volatile compiler option
- /volatile compiler option [C++]
- -volatile compiler option
- volatile compiler option [C++]
- volatile compiler option
- -volatile compiler option [C++]
ms.assetid: 9d08fcc6-5bda-44c8-8151-8d8d54f164b8
caps.latest.revision: "15"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 0e5d138f93aad3603215c3268c2723e0d421b84d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="volatile-volatile-keyword-interpretation"></a>/volatile (volatile Anahtar Sözcük Yorumu)
Belirtir nasıl [volatile](../../cpp/volatile-cpp.md) sözcüktür yorumlanacağını.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/volatile:{iso|ms}  
```  
  
## <a name="arguments"></a>Arguments  
 **/volatile:iso**  
 Katı seçer `volatile` ISO standart C++ dili tarafından tanımlanan şekilde semantiği. Alma/sürüm semantiği geçici erişim sırasında garanti edilmez. Derleyici ARM hedefliyorsa, bu varsayılan yorumu olduğu `volatile`.  
  
 **/volatile:MS**  
 Microsoft genişletilmiş seçer `volatile` garanti ISO standart C++ dili ötesinde sıralama bellek ekleme semantiği. Alma/sürüm semantiği üzerinde geçici erişim sağlanır. Ancak, bu seçenek de önemli ek yükü ARM ve diğer zayıf bellek sıralama mimarileri eklemeleri donanım bellek engelleri oluşturmak için derleyici zorlar. Derleyici ARM dışında herhangi bir platform hedefliyorsa, bu varsayılan yorumu olduğu `volatile`.  
  
## <a name="remarks"></a>Açıklamalar  
 Kullanmanız önerilir **/volatile:iso** açık eşitleme temelleri ve iş parçacıkları arasında paylaşılan bellek ile ilgilenirken derleyici iç bilgileri ile birlikte. Daha fazla bilgi için bkz: [volatile](../../cpp/volatile-cpp.md).  
  
 Bağlantı noktası var olan kodu veya bir proje ortasında bu seçeneği değiştirmek, uyarı etkinleştirmek yararlı olabilir [C4746](../../error-messages/compiler-warnings/compiler-warning-c4746.md) semantiği fark etkilenir kod konumları tanımlamak için.  
  
 Yoktur hiçbir `#pragma` bu seçenek denetim eşdeğerdir.  
  
### <a name="to-set-the-volatile-compiler-option-in-visual-studio"></a>/ Volatile ayarlamak için derleyici seçeneği Visual Studio'da  
  
1.  Açık **özellik sayfaları** projesi için iletişim kutusu. Daha fazla bilgi için bkz: [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Seçin **C/C++** klasör.  
  
3.  Seçin **komut satırı** özellik sayfası.  
  
4.  İçinde **ek seçenekler** kutusunda, eklemek `/volatile:iso` veya `/volatile:ms`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [volatile](../../cpp/volatile-cpp.md)   
 [Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
 [Derleyici seçeneklerini ayarlama](../../build/reference/setting-compiler-options.md)