---
description: "Daha fazla bilgi edinin: Visual C++ 'da MBCS desteği"
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
ms.openlocfilehash: f216e381db8111c54f30b2c2fe326f4914024956
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97207143"
---
# <a name="mbcs-support-in-visual-c"></a>Visual C++'ta MBCS Desteği

Windows 'un MBCS özellikli bir sürümünde çalıştırıldığında, Visual C++ geliştirme sistemi (Tümleşik kaynak kodu Düzenleyicisi, hata ayıklayıcı ve komut satırı araçları dahil), bellek penceresi dışında MBCS etkindir.

Bellek penceresi, verileri ANSI veya Unicode karakterler olarak yorumlayabilse bile, veri baytlarını MBCS karakterleri olarak yorumlamaz. ANSI karakterlerinin boyutu her zaman 1 bayttır ve Unicode karakterler boyutu 2 bayttır. MBCS ile karakterler 1 veya 2 bayt boyutunda olabilir ve bunların yorumu, hangi kod sayfasının kullanımda olduğuna bağlıdır. Bu nedenle, bellek penceresinin MBCS karakterlerini güvenilir bir şekilde görüntülemesi zor olur. Bellek penceresi, karakterin başlangıcını belirten baytı bilmiyor. Geliştirici, bayt değerlerini bellek penceresinde görüntüleyebilir ve karakter gösterimini belirleyebilmek için tablolardaki değeri arayabilir. Geliştirici, kaynak koda göre bir dizenin başlangıç adresini bildiği için bu mümkündür.

Visual C++, doğru olduğu yerde çift baytlık karakterleri kabul eder. Bu, iletişim kutularındaki yol adlarını ve dosya adlarını ve Visual C++ kaynak Düzenleyicisi 'ndeki metin girişlerini (örneğin, iletişim kutusu düzenleyicisinde statik metin ve simge düzenleyicisinde statik metin girişleri) içerir. Ayrıca, Önişlemci bazı çift baytlık yönergeleri (örneğin, ifadelerde dosya adları `#include` ve `code_seg` ve pragmaların bağımsız değişkenleri) tanır `data_seg` . Kaynak kodu düzenleyicisinde, açıklamalarda ve dize değişmez değerlerinde çift baytlık karakterler kabul edilir, ancak C/C++ dil öğelerinde (değişken adları gibi) değil.

## <a name="support-for-the-input-method-editor-ime"></a><a name="_core_support_for_the_input_method_editor_.28.ime.29"></a> Giriş Yöntemi Düzenleyicisi (IME) için destek

MBCS kullanan Doğu Asya pazarları için yazılan uygulamalar (örneğin, Japonya) normalde hem tek hem de çift baytlık karakterler girmek için Windows IME 'YI destekler. Visual C++ geliştirme ortamı, IME için tam destek içerir.

Japonca klavyeler, Kanji karakterlerini doğrudan desteklemez. IME, diğer Japonca alfabellerden birine (Romaji, katakana veya Hiragana), olası Kanji temsillerine girilen bir fonetik dizeyi dönüştürür. Belirsizlik varsa, çeşitli alternatifler arasından seçim yapabilirsiniz. Hedeflenen Kanji karakterini seçtiğinizde, IME `WM_CHAR` denetim uygulamasına iki ileti geçirir.

ALT + tuş birleşimi tarafından etkinleştirilen IME, \` düğme kümesi (bir gösterge) ve dönüştürme penceresi olarak görünür. Uygulama, pencereyi metin ekleme noktasında konumlandırır. Uygulama, `WM_MOVE` `WM_SIZE` hedef pencerenin yeni konumuna veya boyutuna uyacak şekilde dönüştürme penceresini yeniden konumlandırarak, ve iletileri işlemelidir.

Uygulamanızın kullanıcılarının Kanji karakterleri girebilmesini isterseniz, uygulamanın Windows IME iletilerini işlemesi gerekir. IME programlama hakkında daha fazla bilgi için bkz. [giriş yöntemi Yöneticisi](/windows/win32/intl/input-method-manager).

## <a name="visual-c-debugger"></a>Visual C++ hata ayıklayıcı

Visual C++ hata ayıklayıcı IME iletilerinde kesme noktaları ayarlama olanağını sağlar. Ayrıca, bellek penceresinde çift baytlık karakterler görüntülenebilir.

## <a name="command-line-tools"></a>Komut Satırı Araçları

Derleyici, NMAKE ve kaynak derleyicisi (RC.EXE) dahil Visual C++ komut satırı araçları MBCS etkindir. Uygulamanızın kaynaklarını derlerken varsayılan kod sayfasını değiştirmek için Kaynak derleyicinin/c seçeneğini kullanabilirsiniz.

Kaynak kodu derleme zamanında varsayılan yerel ayarı değiştirmek için [#pragma setlocale](../preprocessor/setlocale.md)kullanın.

## <a name="graphical-tools"></a>Grafik araçları

Spy + + ve kaynak düzenlemesi araçları gibi Windows tabanlı Visual C++ araçları, IME dizelerini tamamen destekler.

## <a name="see-also"></a>Ayrıca bkz.

[Çok baytlı karakter kümesi desteği (MBCSs)](../text/support-for-multibyte-character-sets-mbcss.md)<br/>
[MBCS programlama Ipuçları](../text/mbcs-programming-tips.md)
