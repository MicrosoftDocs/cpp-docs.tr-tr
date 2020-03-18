---
title: EDITBIN Seçenekleri
description: Microsoft EDITBIN yardımcı program komut satırı seçeneklerine yönelik başvuru kılavuzu.
ms.date: 02/09/2020
helpviewer_keywords:
- EDITBIN program, options
ms.assetid: 2da9f88e-cbab-4d64-bb66-ef700535230f
ms.openlocfilehash: 9fd4170e5ee020780963d83936f1a9fd08d2be11
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79439966"
---
# <a name="editbin-options"></a>EDITBIN Seçenekleri

Nesne dosyalarını, yürütülebilir dosyaları ve dinamik bağlantı kitaplıklarını (dll 'Ler) değiştirmek için EDITBIN kullanabilirsiniz. Seçenekler EDITBIN 'in yaptığı değişiklikleri belirler.

Bir seçenek, bir tire (`-`) veya eğik çizgi (`/`) ve ardından seçeneğin adı olan bir seçenek belirticisinden oluşur. Seçenek adları kısaltılabilir. Bazı seçenekler, iki nokta üst üste (`:`) sonra belirtilen bağımsız değişkenleri alır. Seçenek belirtimi içinde boşluk veya sekmeye izin verilmez. Komut satırındaki seçenek belirtimlerini ayırmak için bir veya daha fazla boşluk ya da sekme kullanın. Seçenek adları ve anahtar sözcük bağımsız değişkenleri veya dosya adı bağımsız değişkenleri büyük/küçük harfe duyarlı değildir. Örneğin, `-bind` ve `/BIND` aynı şeyi ifade ederler.

EDITBIN aşağıdaki seçeneklere sahiptir:

|Seçenek|Amaç|
|------------|-------------|
|[/ALLOWBIND](allowbind.md)|DLL 'nin bağlanıp bağlanamayacağını belirtir.|
|[/ALLOWISOLATION](allowisolation.md)|DLL veya yürütülebilir dosya bildirimi arama davranışını belirtir.|
|[/APPCONTAINER](appcontainer.md)|Uygulamanın bir AppContainer içinde (örneğin, UWP uygulaması) çalıştırılması gerekip gerekmediğini belirtir.|
|[/BIND](bind.md)|Yükleme süresini hızlandırmak için belirtilen nesnelerdeki giriş noktalarının adreslerini ayarlar.|
|[/DYNAMICBASE](dynamicbase.md)|DLL veya yürütülebilir görüntünün, adres alanı düzeni rastgele seçme (ASLR) kullanılarak yük zamanında rastgele bir şekilde yeniden yapılıp yapılmayacağını belirtir.|
|[/ERRORREPORT](errorreport-editbin-exe.md)| Kullanım dışı. Hata raporlama [Windows hata bildirimi (WER)](/windows/win32/wer/windows-error-reporting) ayarları tarafından denetlenir. |
|[/HEAP](heap.md)|Yürütülebilir görüntünün yığınının bayt cinsinden boyutunu ayarlar.|
|[/HIGHENTROPYVA](highentropyva.md)|DLL veya yürütülebilir görüntünün yüksek entropi (64-bit) adres alanı düzeni rastgele seçme (ASLR) öğesini destekleyip desteklemediğini belirtir.|
|[/INTEGRITYCHECK](integritycheck.md)|Yükleme sırasında dijital imzanın denetleyip denetedilmeyeceğini belirtir.|
|[/LARGEADDRESSAWARE](largeaddressaware.md)|Nesnenin iki gigabayttan daha büyük olan adresleri destekleyip desteklemediğini belirtir.|
|[/NOLOGO](nologo-editbin.md)|EDITBIN başlangıç başlığını gizler.|
|[/NXCOMPAT](nxcompat.md)|Yürütülebilir görüntünün Windows veri yürütme engellemesi ile uyumlu olup olmadığını belirtir.|
|[/REBASE](rebase.md)|Belirtilen nesnelerin taban adreslerini ayarlar.|
|[/RELEASE](release.md)|Başlıktaki sağlama toplamını ayarlar.|
|[/SECTıON](section-editbin.md)|Bir bölümün özniteliklerini geçersiz kılar.|
|[/STACK](stack.md)|Yürütülebilir görüntünün yığınının boyutunu bayt cinsinden ayarlar.|
|[/SUBSYSTEM](subsystem.md)|Yürütme ortamını belirtir.|
|[/SWAPRUN](swaprun.md)|Yürütülebilir görüntünün takas dosyasına kopyalandığını belirtir ve sonra buradan çalıştırın.|
|[/TSAWARE](tsaware.md)|Uygulamanın bir çoklu kullanıcı ortamında çalışacak şekilde tasarlandığını belirtir.|
|[/VERSION](version.md)|Başlıktaki sürüm numarasını ayarlar.|

## <a name="see-also"></a>Ayrıca bkz.

[Ek MSVC derleme araçları](c-cpp-build-tools.md)\
[EDITBIN Başvurusu](editbin-reference.md)
