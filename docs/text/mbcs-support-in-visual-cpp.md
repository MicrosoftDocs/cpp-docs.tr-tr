---
title: "Visual C++'ta MBCS Desteği | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: _mbcs
dev_langs: C++
helpviewer_keywords:
- tools [C++], MBCS support
- Asian languages [C++]
- Code Editor [C++], MBCS support
- IME [C++]
- Chinese characters [C++]
- Input Method Editor [C++], MBCS
- resource editors [C++], MBCS support
- debugger [C++], MBCS support
- character sets [C++], multibyte
- Japanese characters [C++]
- multibyte characters [C++]
- Kanji character support [C++]
- NMAKE program, MBCS support
- double-byte character sets [C++]
- IME [C++], MBCS
- Input Method Editor [C++]
- MBCS [C++], enabling
ms.assetid: 6179f6b7-bc61-4a48-9267-fb7951223e38
caps.latest.revision: "7"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.openlocfilehash: 65d5fc64db1e43d9b0914a9d8671e466f4ee87e6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="mbcs-support-in-visual-c"></a>Visual C++'ta MBCS Desteği
Bir MBCS etkinleştirilmiş Windows 2000 veya Windows XP işletim sistemi sürümünde çalıştırdığınızda (tümleşik kaynak kod düzenleyicisinde, hata ayıklayıcı ve komut satırı araçları dahil) Visual C++ geliştirme MBCS etkinleştirilmiş, bellek penceresi dışında sistemidir.  
  
 ANSI veya Unicode karakter olarak bunlara çevirebilir olsa bile bellek penceresi bayt veri MBCS karakter olarak yorumlayın değil. ANSI karakter her zaman 1 bayt boyutunda ve Unicode karakterler 2 bayt cinsinden boyutu. MBCS ile karakterler 1 veya 2 bayt boyutunda olabilir ve kendi yorum hangi kod sayfası kullanımda olduğuna bağlıdır. Bu nedenle, güvenilir bir şekilde MBCS karakterleri görüntülemek bellek penceresi zor olabilir. Bellek penceresi hangi bayt karakter başlangıcıdır bilemezsiniz. Geliştirici bayt değerlerini bellek penceresinde görüntüleyebilir ve karakter gösterimi belirlemek için tabloları değeri bakın. Başlangıç adresi kaynak koduna göre bir dize olarak Geliştirici bildiği için bu mümkün olur.  
  
 Bunu yapmak uygun olduğu yerlerde visual C++ çift baytlık karakterler kabul eder. Bu yol adlarını ve dosya adlarını iletişim kutularında ve metin girişleri Visual C++ kaynak düzenleyicisinde (örneğin, statik metin iletişim kutusu Düzenleyicisi) ve simge düzenleyicideki statik metin girişleri içerir. Ayrıca, bazı çift baytlık yönergeleri önişlemci tanır — Örneğin, dosya adları `#include` deyimleri ve bağımsız değişkenleri olarak **code_seg** ve **data_seg** pragmaları. Kaynak Kodu Düzenleyicisi'nde, açıklamalar ve dize değişmez değerleri çift baytlık karakterler, C/C++ dil öğeleri olsa da (örneğin, değişken adları) içinde değil kabul edilir.  
  
##  <a name="_core_support_for_the_input_method_editor_.28.ime.29"></a>Giriş Yöntemi Düzenleyicisi (IME) için destek  
 Hem tek ve çift baytlık karakterler girmek için Windows IME MBCS (örneğin, Japonya) normalde kullandığınız Doğu Asya pazarda desteği için yazılmış uygulamalar. Visual C++ geliştirme ortamı IME için tam destek içerir. Daha fazla bilgi için bkz: [IME örnek: denetim IME modu ve uygulama IME düzeyi 3'ü nasıl gösteren](http://msdn.microsoft.com/en-us/87ebdf65-cef0-451d-a6fc-d5fb64178b14).  
  
 Japonca klavye Kanji karakter doğrudan desteklemez. IME diğer Japonca alfabesinde (Romaji, Katakana veya Hiragana) birine kendi olası Kanji Beyanları girdiğiniz bir ses dizesi dönüştürür. Belirsizliği ise, birkaç alternatif arasından seçebilirsiniz. Hedeflenen Kanji karakter seçildiğinde IME iki geçirir `WM_CHAR` denetleyen uygulama iletileri.  
  
 ALT + tarafından etkinleştirilmiş IME\` tuş bileşimi, bir dizi düğmeler (bir gösterge) ve bir dönüştürme pencere görünür. Uygulama penceresi metin ekleme noktasına yerleştirir. Uygulama işlemelidir `WM_MOVE` ve `WM_SIZE` yeni konumu veya hedef penceresi boyutunu uyacak şekilde dönüştürme penceresini yeniden konumlandırma tarafından iletileri.  
  
 Kanji karakter girin olanağı sağlamak için uygulamanızın kullanıcılarının istiyorsanız, uygulamanın Windows IME iletilerini işlemesi gerekir. IME programlama hakkında daha fazla bilgi için bkz: [Giriş Yöntemi Düzenleyicisi](https://msdn.microsoft.com/en-us/library/ms776145.aspx).  
  
## <a name="visual-c-debugger"></a>Visual C++ hata ayıklayıcı  
 Visual C++ hata ayıklayıcı IME iletileri üzerindeki kesme noktaları ayarlamanıza olanak sağlar. Ayrıca, bellek penceresi çift baytlık karakterler görüntüleyebilirsiniz.  
  
## <a name="command-line-tools"></a>Komut Satırı Araçları  
 Derleyici, NMAKE ve kaynak derleyicisi (RC. dahil olmak üzere Visual C++ komut satırı araçları EXE) MBCS etkinleştirilmiştir. Varsayılan kod sayfası, uygulamanızın kaynakları derlerken değiştirmek için kaynak derleyicinin /c seçeneğini kullanabilirsiniz.  
  
 Kaynak kodu derleme zamanında varsayılan yerel ayar değiştirmek için kullanın [#pragma setlocale](../preprocessor/setlocale.md).  
  
## <a name="graphical-tools"></a>Grafik araçları  
 Spy ++ ve düzenleme araçları, kaynak gibi Visual C++ Windows tabanlı araçlar IME dizelerini tümüyle destekler.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çok baytlı karakter kümeleri (MBCS'ler) desteği](../text/support-for-multibyte-character-sets-mbcss.md)   
 [MBCS programlama ipuçları](../text/mbcs-programming-tips.md)