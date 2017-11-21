---
title: "Uluslararası etkinleştirme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- globalization [C++], character sets
- strings [C++], international enabling
- localization [C++], character sets
- MBCS [C++], enabling
- Unicode [C++], enabling
ms.assetid: b077f4ca-5865-40ef-a46e-d9e4d686ef21
caps.latest.revision: "7"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.openlocfilehash: d075ccda653ed04722026d5f1ab71ff83a4936db
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="international-enabling"></a>Uluslararası Etkinleştirme
Çoğu geleneksel C ve C++ kodu uluslararası uygulamalarda düzgün çalışmayan varsayımlarda karakter ve dize hakkında bulunur. MFC ve çalışma zamanı kitaplığı Unicode ya da MBCS desteklerken, da hala yapmanız gereken iş yok. Size yol göstermesi için bu bölümde Visual c++'ta "uluslararası etkinleştirme" anlamı açıklanmaktadır:  
  
-   Unicode ve MBCS MFC işlevi parametresi listelerinde taşınabilir veri türleri yoluyla etkin ve dönüş türleri. Bu tür koşullu simgenin olup tanımladığına bağlı olarak uygun şekilde tanımlanır **_UNICODE** veya sembol **_MBCS** (yani DBCS). MFC kitaplıkları farklı türevleri, bu iki simgeleri bağlı olarak tanımladığına uygulamanızla birlikte otomatik olarak bağlanır.  
  
-   Sınıf kitaplığı kodu, doğru Unicode ya da MBCS davranışını sağlamak için taşınabilir çalışma zamanı işlevleri ve diğer yolları kullanır.  
  
-   Kodunuzda belirli duruma getirme görevlerini hala işlemesi gerekir:  
  
    -   MFC altında herhangi bir ortamda taşınabilir hale aynı taşınabilir çalışma zamanı işlevleri kullanın.  
  
    -   Değişmez değer dizeleri ve karakterleri herhangi bir ortamda altında taşınabilir hale kullanarak **_T** makrosu. Daha fazla bilgi için bkz: [Tchar.h'de genel metin eşlemeleri](../text/generic-text-mappings-in-tchar-h.md).  
  
    -   MBCS altında dizeleri ayrıştırırken önlemleri alın. Unicode altında şunlara gerekli değildir. Daha fazla bilgi için bkz: [MBCS programlama ipuçları](../text/mbcs-programming-tips.md).  
  
    -   Uygulamanızda ANSI (8-bit) ve Unicode (16-bit) karakterleri karıştırmak istiyorsanız dikkatli olun. Bazı bölümleri programınızın ANSI karakter ve diğerleri Unicode karakterler kullanmak da mümkündür, ancak aynı dizede karıştıramazsınız.  
  
    -   Uygulamanızda olmayan sabit kod dizeleri yapın. Bunun yerine, bunları uygulamanın .rc dosyasına ekleyerek STRINGTABLE kaynakları yapın. Uygulamanızın kaynak kodunu değişiklikleri ya da yeniden derleme gerektirmeden sonra yerelleştirilmiş olmalıdır. STRINGTABLE kaynakları hakkında daha fazla bilgi için bkz: [Dize Düzenleyicisi](../windows/string-editor.md).  
  
> [!NOTE]
>  Karakter kodları 0x80'den büyük olan aksanlı harfler gibi bazı karakterler Avrupa ve MBCS karakter kümesi vardır. Çoğu kod işaretli karakterler kullandığından, 0x80'den büyük bu karakterler için dönüştürüldüğünde oturum Genişletilmiş `int`. Negatif olan oturum genişletilmiş karakterler dizinler dizinin dışına dizi dizin oluşturma için bir sorun olmasıdır. Japonca gibi MBCS kullanan diller de benzersizdir. 1 veya 2 bayt karakter oluşabilir olduğundan her zaman aynı anda hem bayt değiştirmelisiniz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Unicode ve MBCS](../text/unicode-and-mbcs.md)   
 [Uluslararası duruma getirme stratejileri](../text/internationalization-strategies.md)