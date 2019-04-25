---
title: EDITBIN Seçenekleri
ms.date: 11/04/2016
f1_keywords:
- editbin
helpviewer_keywords:
- EDITBIN program, options
ms.assetid: 2da9f88e-cbab-4d64-bb66-ef700535230f
ms.openlocfilehash: e7338c6a45d74aa8efac1b72683cca7661c62e0a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62271859"
---
# <a name="editbin-options"></a>EDITBIN Seçenekleri

Nesne dosyaları, yürütülebilir dosyalar ve dinamik bağlantı kitaplıklarını (DLL'ler) değiştirileceğini EDITBIN kullanabilirsiniz. EDITBIN yaptığı değişiklikler seçeneklerini belirtin.

İsteğe bağlı bir tire (-) ya da seçenek adından önce gelen bir eğik çizgi (/), bir seçenek belirticisi oluşur. Seçenek adları kısaltılmış olamaz. Bazı seçenekler, iki nokta (:) sonra belirtilen bağımsız değişken almaz. Boşluk veya sekme içinde bir seçenek belirtimine izin verilir. Komut satırı seçeneği belirtimlerine ayırmak için bir veya daha fazla boşluk veya sekme kullanın. Seçenek adları ve anahtar sözcük bağımsız değişkenleri veya dosya adı bağımsız değişkenler büyük küçük harfe duyarlı değildir. Örneğin, - bağlama ve/Bind için de aynı anlama gelir.

EDITBIN şu seçeneklere sahiptir:

|Seçenek|Amaç|
|------------|-------------|
|[/ALLOWBIND](allowbind.md)|DLL'in bağlı olamayacağını belirtir.|
|[/ALLOWISOLATION](allowisolation.md)|DLL veya yürütülebilir dosya bildirim arama davranışını belirtir.|
|[/APPCONTAINER](appcontainer.md)|Uygulamanın bir AppContainer içinde çalışmasının gerekip gerekmediğini belirtir; örneğin, bir UWP uygulaması.|
|[/BIND](bind.md)|Giriş noktaları için adresleri belirtilen nesnelerin yükleme süresini hızlandırmak için ayarlar.|
|[/DYNAMICBASE](dynamicbase.md)|DLL veya yürütülebilir görüntü rastgele yükleme zamanında rastgele adres alanı düzenini (ASLR) temellendirilebilen olup olmadığını belirtir.|
|[/ ERRORREPORT](errorreport-editbin-exe.md)|İç hatalarını Microsoft'a bildirir.|
|[/HEAP](heap.md)|Yürütülebilir resmin yığın boyutunu bayt cinsinden ayarlar.|
|[/HIGHENTROPYVA](highentropyva.md)|DLL veya yürütülebilir resmin yüksek entropi (64-bit) rastgele adres alanı düzenini (ASLR) destekleyip desteklemediğini belirtir.|
|[/INTEGRITYCHECK](integritycheck.md)|Yükleme zamanında dijital imza denetlenip denetlenmeyeceğini belirtir.|
|[/LARGEADDRESSAWARE](largeaddressaware.md)|Nesne iki gigabayttan büyük adresleri destekleyip desteklemediğini belirtir.|
|[/ NOLOGO](nologo-editbin.md)|EDITBIN Başlangıç başlığını göstermez.|
|[/NXCOMPAT](nxcompat.md)|Yürütülebilir resmin Windows veri yürütme önlemesi ile uyumlu olup olmadığını belirtir.|
|[/REBASE](rebase.md)|Belirtilen nesneler için temel adres ayarlar.|
|[/RELEASE](release.md)|Üst bilgisinde sağlama toplamını ayarlar.|
|[/ SECTION](section-editbin.md)|Bir bölümün özniteliklerini geçersiz kılar.|
|[/STACK](stack.md)|Yürütülebilir resmin yığın boyutunu bayt cinsinden ayarlar.|
|[/SUBSYSTEM](subsystem.md)|Yürütme ortamını belirtir.|
|[/SWAPRUN](swaprun.md)|Yürütülebilir resmin gerekir takas dosyasına kopyalanır ve ardından oradan çalıştırın belirtir.|
|[/TSAWARE](tsaware.md)|Uygulama, çok kullanıcılı ortamda çalıştırmak için tasarlanmıştır belirtir.|
|[/VERSION](version.md)|Üst bilgisinde sürüm numarasını ayarlar.|

## <a name="see-also"></a>Ayrıca bkz.

[Ek MSVC derleme araçları](c-cpp-build-tools.md)<br/>
[EDITBIN Başvurusu](editbin-reference.md)
