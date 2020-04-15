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
ms.openlocfilehash: 404fcee5e48d8db28e56a005f24f8cac5892240e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375789"
---
# <a name="mbcs-support-in-visual-c"></a>Visual C++'ta MBCS Desteği

Windows'un MBCS özellikli sürümünde çalıştırıldığında, Visual C++ geliştirme sistemi (tümleşik kaynak kod düzenleyicisi, hata ayıklayıcı ve komut satırı araçları dahil) bellek penceresi dışında MBCS özelliklidir.

Bellek penceresi, ansi veya Unicode karakterleri olarak yorumlayabilse de, bayt verileri MBCS karakterleri olarak yorumlamaz. ANSI karakterleri her zaman 1 bayt boyutunda ve Unicode karakterleri boyutu 2 bayt vardır. MBCS ile karakterler boyutu 1 veya 2 bayt olabilir ve bunların yorumlanması hangi kod sayfasının kullanıldığına bağlıdır. Bu nedenle, bellek penceresinin MBCS karakterlerini güvenilir bir şekilde görüntülemesi zordur. Bellek penceresi hangi baytın bir karakterin başlangıcı olduğunu bilemez. Geliştirici bellek penceresinde bayt değerlerini görüntüleyebilir ve karakter gösterimini belirlemek için tablolardaki değeri arar. Geliştirici kaynak koduna dayalı bir dize başlangıç adresini bildiği için bu mümkündür.

Visual C++ çift bayt karakterleri uygun olduğu her yerde kabul eder. Buna, Visual C++ kaynak düzenleyicisindeki iletişim kutularındaki yol adları ve dosya adları ve metin girişleri (örneğin, iletişim düzenleyicisindeki statik metin ve simge düzenleyicisindeki statik metin girişleri) dahildir. Buna ek olarak, önişlemci bazı çift bayt yönergeleri tanır - `#include` örneğin, ifadelerde `code_seg` dosya `data_seg` adları ve ve pragmas bağımsız değişkenleri olarak. Kaynak kod düzenleyicisinde, C/C++ dil öğelerinde (değişken adları gibi) olmasa da, yorumlardaki ve string literals'deki çift bayt karakterleri kabul edilir.

## <a name="support-for-the-input-method-editor-ime"></a><a name="_core_support_for_the_input_method_editor_.28.ime.29"></a>Giriş Yöntemi Düzenleyicisi (IME) desteği

MBCS (örneğin, Japonya) kullanan Doğu Asya pazarları için yazılmış uygulamalar normalde hem tek hem de çift bayt karakter girmek için Windows IME'yi destekler. Visual C++ geliştirme ortamı IME için tam destek içerir.

Japonca klavyeler Kanji karakterlerini doğrudan desteklemez. IME, diğer Japon alfabelerinden (Romaji, Katakana veya Hiragana) girilen fonetik bir dizeyi olası Kanji temsillerine dönüştürür. Belirsizlik varsa, birkaç alternatif arasından seçim yapabilirsiniz. Amaçlanan Kanji karakterini seçtiğinizde, IME `WM_CHAR` denetleme uygulamasına iki ileti aktarAr.

ALT+\` tuşu kombinasyonu tarafından etkinleştirilen IME, bir düğme kümesi (gösterge) ve dönüşüm penceresi olarak görünür. Uygulama pencereyi metin ekleme noktasına konumlandırın. Uygulama, dönüşüm `WM_MOVE` `WM_SIZE` penceresini yeni konuma veya hedef pencerenin boyutuna uyacak şekilde yeniden konumlandırarak işlemeli ve iletileri ele almalıdır.

Uygulamanızın kullanıcılarının Kanji karakterlerini girebilmesini istiyorsanız, uygulamanın Windows IME iletilerini işlemesi gerekir. IME programlama hakkında daha fazla bilgi için [Giriş Yöntemi Yöneticisi'ne](/windows/win32/intl/input-method-manager)bakın.

## <a name="visual-c-debugger"></a>Görsel C++ Debugger

Visual C++ hata ayıklama, IME iletilerinde kesme noktaları ayarlama olanağı sağlar. Buna ek olarak, Bellek penceresi çift bayt karakterleri görüntüleyebilir.

## <a name="command-line-tools"></a>Komut Satırı Araçları

Derleyici, NMAKE ve kaynak derleyicisi (RC) dahil olmak üzere Visual C++ komut satırı araçları. EXE), MBCS özelliklidir. Uygulamanızın kaynaklarını derlerken varsayılan kod sayfasını değiştirmek için kaynak derleyicisinin /c seçeneğini kullanabilirsiniz.

Kaynak kodunda varsayılan yerel alanı değiştirmek için zaman derleme süresini #pragma [ayarlayın.](../preprocessor/setlocale.md)

## <a name="graphical-tools"></a>Grafik Araçları

Spy++ ve kaynak düzenleme araçları gibi Visual C++ Windows tabanlı araçlar IME dizelerini tam olarak destekler.

## <a name="see-also"></a>Ayrıca bkz.

[Çok Baytlı Karakter Kümesi Desteği (MBCS'ler)](../text/support-for-multibyte-character-sets-mbcss.md)<br/>
[MBCS Programlama İpuçları](../text/mbcs-programming-tips.md)
