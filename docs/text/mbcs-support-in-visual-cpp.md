---
title: Visual C++'ta MBCS Desteği
ms.date: 11/04/2016
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
ms.openlocfilehash: b5f2b6dd56d3a755ee73058c024152e12157a6bd
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69501941"
---
# <a name="mbcs-support-in-visual-c"></a>Visual C++'ta MBCS Desteği

Windows 'un MBCS özellikli bir sürümünde çalıştırıldığında, Visual C++ geliştirme sistemi (Tümleşik kaynak kodu Düzenleyicisi, hata ayıklayıcı ve komut satırı araçları dahil), bellek PENCERESI dışında MBCS etkindir.

Bellek penceresi, verileri ANSI veya Unicode karakterler olarak yorumlayabilse bile, veri baytlarını MBCS karakterleri olarak yorumlamaz. ANSI karakterlerinin boyutu her zaman 1 bayttır ve Unicode karakterler boyutu 2 bayttır. MBCS ile karakterler 1 veya 2 bayt boyutunda olabilir ve bunların yorumu, hangi kod sayfasının kullanımda olduğuna bağlıdır. Bu nedenle, bellek penceresinin MBCS karakterlerini güvenilir bir şekilde görüntülemesi zor olur. Bellek penceresi, karakterin başlangıcını belirten baytı bilmiyor. Geliştirici, bayt değerlerini bellek penceresinde görüntüleyebilir ve karakter gösterimini belirleyebilmek için tablolardaki değeri arayabilir. Geliştirici, kaynak koda göre bir dizenin başlangıç adresini bildiği için bu mümkündür.

Görsel C++ , doğru olduğu yerde çift baytlık karakterler kabul eder. Bu, iletişim kutularındaki yol adlarını ve dosya adlarını ve görsel C++ kaynak Düzenleyicisi 'ndeki metin girişlerini (örneğin, iletişim kutusu düzenleyicisinde statik metin ve simge düzenleyicisinde statik metin girişleri) içerir. Ayrıca, Önişlemci bazı çift baytlık yönergeleri (örneğin, `#include` ifadelerde dosya adları ve `code_seg` ve `data_seg` pragmaların bağımsız değişkenleri) tanır. Kaynak kodu düzenleyicisinde, açıklamalarda ve dize değişmez değerlerinde çift baytlık karakterler kabul edilir, ancak C/C++ Language öğelerinde (değişken adları gibi) değil.

##  <a name="_core_support_for_the_input_method_editor_.28.ime.29"></a>Giriş Yöntemi Düzenleyicisi (IME) için destek

MBCS kullanan Doğu Asya pazarları için yazılan uygulamalar (örneğin, Japonya) normalde hem tek hem de çift baytlık karakterler girmek için Windows IME 'YI destekler. Görsel C++ geliştirme ORTAMı, IME için tam destek içerir.

Japonca klavyeler, Kanji karakterlerini doğrudan desteklemez. IME, diğer Japonca alfabellerden birine (Romaji, katakana veya Hiragana), olası Kanji temsillerine girilen bir fonetik dizeyi dönüştürür. Belirsizlik varsa, çeşitli alternatifler arasından seçim yapabilirsiniz. Hedeflenen Kanji karakterini seçtiğinizde, IME denetim uygulamasına iki `WM_CHAR` ileti geçirir.

ALT +\` tuş birleşimi tarafından etkinleştirilen IME, düğme kümesi (bir gösterge) ve dönüştürme penceresi olarak görünür. Uygulama, pencereyi metin ekleme noktasında konumlandırır. Uygulama, hedef pencerenin `WM_MOVE` yeni `WM_SIZE` konumuna veya boyutuna uyacak şekilde dönüştürme penceresini yeniden konumlandırarak, ve iletileri işlemelidir.

Uygulamanızın kullanıcılarının Kanji karakterleri girebilmesini isterseniz, uygulamanın Windows IME iletilerini işlemesi gerekir. IME programlama hakkında daha fazla bilgi için bkz. [giriş yöntemi Yöneticisi](/windows/win32/intl/input-method-manager).

## <a name="visual-c-debugger"></a>Görsel C++ hata ayıklayıcı

Görsel C++ hata AYıKLAYıCı, IME iletilerinde kesme noktaları ayarlama yeteneği sağlar. Ayrıca, bellek penceresinde çift baytlık karakterler görüntülenebilir.

## <a name="command-line-tools"></a>Komut Satırı Araçları

Derleyici, C++ NMAKE ve kaynak derleyicisi (RC) dahil olmak üzere görsel komut satırı araçları (RC. EXE), MBCS etkindir. Uygulamanızın kaynaklarını derlerken varsayılan kod sayfasını değiştirmek için Kaynak derleyicinin/c seçeneğini kullanabilirsiniz.

Kaynak kodu derleme zamanında varsayılan yerel ayarı değiştirmek için [#pragma setlocale](../preprocessor/setlocale.md)kullanın.

## <a name="graphical-tools"></a>Grafik araçları

Spy + C++ + ve kaynak düzenlemesi araçları gibi Visual Windows tabanlı araçlar, IME dizelerini tamamen destekler.

## <a name="see-also"></a>Ayrıca bkz.

[Çok Baytlı Karakter Kümesi Desteği (MBCS'ler)](../text/support-for-multibyte-character-sets-mbcss.md)<br/>
[MBCS Programlama İpuçları](../text/mbcs-programming-tips.md)
