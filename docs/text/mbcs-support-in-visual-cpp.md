---
title: Visual C++'ta MBCS Desteği | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- _mbcs
dev_langs:
- C++
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
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1d00495f95b3c67e4a6fc3613b949b8ae2946bd6
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40010392"
---
# <a name="mbcs-support-in-visual-c"></a>Visual C++'ta MBCS Desteği
Bir MBCS etkinleştirilmiş Windows sürümünde çalıştırdığınızda (tümleşik Kaynak Kod Düzenleyicisi, hata ayıklayıcı ve komut satırı araçları dahil) Visual C++ geliştirme MBCS özellikli, bellek penceresi dışında sistemidir.  
  
 Bellek penceresi, ANSI veya Unicode karakteri yorumlayabilir olsa bile verileri baytlık MBCS karakter olarak yorumlamaz. ANSI karakterler her zaman boyutu 1 bayt ve Unicode karakterleri 2 bayt cinsinden boyutu. MBCS ile karakter, 1 veya 2 bayt boyutunda olabilir ve kendi yorumu hangi kod sayfası kullanımda olduğuna bağlıdır. Bu nedenle, güvenilir bir şekilde MBCS karakter görüntülemek bellek penceresi zordur. Bellek penceresi bir karakter başlangıcı hangi baytı olup olmadığını bilemezsiniz. Geliştirici bellek penceresinde bayt değerleri görüntüleyebilir ve karakter gösterimi belirlemek için tabloları değerini arayın. Geliştirici kaynak koduna göre bir dizenin başlangıç adresini bilmesi için bu olasıdır.  
  
 Bunu yapmak uygun olduğu yerlerde visual C++ çift baytlık karakterler kabul eder. Bu yol adları ve dosya adlarını iletişim kutuları ve Visual C++ kaynak Düzenleyicisi (örneğin, statik metin iletişim kutusu düzenleyicisinde) ve simge Düzenleyicisi statik metin girişleri metin girişleri içerir. Ayrıca, önişlemci bazı çift bayt yönergeleri tanır; Örneğin, dosya adları `#include` deyimleri ve bağımsız değişkenleri olarak `code_seg` ve `data_seg` pragmaları. Kaynak Kod Düzenleyicisi'nde çift baytlık karakterler yorumlar ve dize değişmez değerleri, olmayan C/C++ Dil öğelerini rağmen (örneğin, değişken adları) olarak kabul edilir.  
  
##  <a name="_core_support_for_the_input_method_editor_.28.ime.29"></a> Giriş Yöntemi Düzenleyicisi (IME) için destek  
 MBCS (örneğin, Japonya) normalde kullandığınız Doğu Asya pazarları için hem tek ve çift baytlık karakterler girerek Windows IME desteği için yazılmış uygulamalar. Visual C++ geliştirme ortamına IME için tam destek içerir. Daha fazla bilgi için [IME örnek: denetim IME modu ve uygulama IME Düzey 3'ü nasıl gösterir](http://msdn.microsoft.com/87ebdf65-cef0-451d-a6fc-d5fb64178b14).  
  
 Japonca klavye Kanji karakter doğrudan desteklemez. IME diğer Japonca alfabelere (Romaji, Katakana veya Hiragana) birinde, olası Kanji gösterimleri girilen bir ses dizesi dönüştürür. Belirsizlik varsa, birkaç alternatif arasından seçebilirsiniz. Hedeflenen Kanji karakter seçtikten sonra iki IME geçirir `WM_CHAR` iletileri denetleme uygulama.  
  
 ALT + tarafından etkinleştirilmiş IME\` tuş bileşimi, bir dizi düğmeler (bir göstergesi) ve bir dönüştürme pencere görüntülenir. Uygulama penceresi metin ekleme noktasından yerleştirir. Uygulama işlemelidir `WM_MOVE` ve `WM_SIZE` yeni konumu veya hedef penceresinin boyutunu uyacak şekilde dönüştürme penceresi yeniden konumlandırma tarafından iletileri.  
  
 Kullanıcıların uygulamanızın Kanji karakter girmeniz becerisine sahip olmak istiyorsanız, uygulamanın Windows IME iletileri işlemesi gerekir. IME programlama hakkında daha fazla bilgi için bkz. [Giriş Yöntemi Düzenleyicisi](https://msdn.microsoft.com/library/ms776145.aspx).  
  
## <a name="visual-c-debugger"></a>Visual C++ hata ayıklayıcı  
 Visual C++ hata ayıklayıcı, kesme noktaları IME iletileri ayarlamanıza olanak sağlar. Ayrıca, bellek penceresini çift baytlık karakterler görüntüleyebilirsiniz.  
  
## <a name="command-line-tools"></a>Komut Satırı Araçları  
 Derleyici, NMAKE ve kaynak derleyicisi (RC. dahil olmak üzere Visual C++ komut satırı araçları EXE) MBCS etkinleştirilmiştir. Kaynak derleyicinin /c seçeneği, varsayılan kod sayfası, uygulamanızın kaynakları derlenirken değiştirmek için kullanabilirsiniz.  
  
 Kaynak kodu derleme zamanında varsayılan yerel ayarı değiştirmek için kullanın [#pragma setlocale](../preprocessor/setlocale.md).  
  
## <a name="graphical-tools"></a>Grafik araçları  
 Visual C++ Windows tabanlı araçlar Spy ++ ve düzenleme araçları, kaynak gibi IME dizeleri tam olarak destekler.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çok baytlı karakter kümesi desteği (MBCS'ler)](../text/support-for-multibyte-character-sets-mbcss.md)   
 [MBCS Programlama İpuçları](../text/mbcs-programming-tips.md)