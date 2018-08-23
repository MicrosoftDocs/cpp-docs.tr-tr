---
title: Uluslararası etkinleştirme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- globalization [C++], character sets
- strings [C++], international enabling
- localization [C++], character sets
- MBCS [C++], enabling
- Unicode [C++], enabling
ms.assetid: b077f4ca-5865-40ef-a46e-d9e4d686ef21
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b63801ac98027f490463f36df23541993528d33b
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42596204"
---
# <a name="international-enabling"></a>Uluslararası Etkinleştirme
Uluslararası uygulamalar için düzgün çalışmayan karakter ve dize hakkında varsayımlar çoğu geleneksel C ve C++ kodu sağlar. MFC ve çalışma zamanı kitaplığı Unicode veya MBCS desteklese de da hala yapmanız iş yok. Size yol göstermesi için bu bölümde Visual C++'da "uluslararası etkinleştirme" ne anlama geldiğini açıklanmaktadır:  
  
-   Unicode ve MBCS MFC işlev parametre listeleri taşınabilir veri türleri yoluyla etkin ve dönüş türleri. Bu tür simge olup tanımladığına bağlı olarak uygun şekilde koşullu olarak tanımlanmıştır `_UNICODE` veya sembol `_MBCS` (yani DBCS). MFC kitaplıkları farklı çeşitlerini bağlı olarak, bu iki simge tanımladığına uygulamanızla birlikte otomatik olarak bağlanır.  
  
-   Sınıf kitaplığı kodunu Unicode veya MBCS doğru davranışı sağlamak açısından taşınabilir çalışma zamanı işlevleri ve diğer yolları kullanır.  
  
-   Kodunuzda belirli duruma getirme görevlerini hala işlemesi gerekir:  
  
    -   MFC altında herhangi bir ortamda taşınabilir hale aynı taşınabilir çalışma zamanı işlevleri kullanın.  
  
    -   Değişmez değer dizeleri ve karakter herhangi bir ortamda altında taşınabilir hale kullanarak `_T` makrosu. Daha fazla bilgi için [Tchar.h'de genel metin eşlemeleri](../text/generic-text-mappings-in-tchar-h.md).  
  
    -   MBCS altında dizelere ayrıştırılırken önlemleri alın. Unicode altında şunlara gerekli değildir. Daha fazla bilgi için [MBCS programlama ipuçları](../text/mbcs-programming-tips.md).  
  
    -   Uygulamanızda ANSI (8-bit) ve Unicode (16-bit) karakter karışımı varsa ilgileniriz. ANSI programınızın bazı bölümlerinde, Unicode karakter diğerleri kullanmak da mümkündür, ancak aynı dizesinde karıştırılamaz.  
  
    -   Uygulamanızı sabit dizelerde yapın. Bunun yerine, bunları STRINGTABLE kaynakları uygulamanın .rc dosyasına ekleyerek olun. Uygulamanızın kaynak kodu değişiklikleri veya yeniden derleme gerek kalmadan ardından yerelleştirilmiş olmalıdır. STRINGTABLE kaynakları hakkında daha fazla bilgi için bkz. [Dize Düzenleyicisi](../windows/string-editor.md).  
  
> [!NOTE]
>  Bazı karakterler, aksanlı harfler, 0x80'den büyük olan karakter kodlarını gibi Avrupa ve MBCS karakter kümesi vardır. Çoğu kod imzalı karakterler kullandığından, 0x80'den büyük bu karakterler için dönüştürüldüğünde işaret Genişletilmiş **int**. Negatif olan işaret Genişletilmiş karakter dizinini oluşturan dizinin dışında dizi dizini oluşturma için bir sorun olmasıdır. Japonca gibi bir MBCS kullanan diller de benzersizdir. Bir karakter, 1 veya 2 bayt oluşabilir olduğundan her zaman aynı anda iki bayt değiştirmelisiniz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Unicode ve MBCS](../text/unicode-and-mbcs.md)   
 [Uluslararası Duruma Getirme Stratejileri](../text/internationalization-strategies.md)