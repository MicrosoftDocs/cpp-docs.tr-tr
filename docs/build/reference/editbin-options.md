---
title: EDITBIN seçenekleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- editbin
dev_langs:
- C++
helpviewer_keywords:
- EDITBIN program, options
ms.assetid: 2da9f88e-cbab-4d64-bb66-ef700535230f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0850f242b8368a9592a5622e627c781b4df4cde5
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45710144"
---
# <a name="editbin-options"></a>EDITBIN Seçenekleri

Nesne dosyaları, yürütülebilir dosyalar ve dinamik bağlantı kitaplıklarını (DLL'ler) değiştirileceğini EDITBIN kullanabilirsiniz. EDITBIN yaptığı değişiklikler seçeneklerini belirtin.

İsteğe bağlı bir tire (-) ya da seçenek adından önce gelen bir eğik çizgi (/), bir seçenek belirticisi oluşur. Seçenek adları kısaltılmış olamaz. Bazı seçenekler, iki nokta (:) sonra belirtilen bağımsız değişken almaz. Boşluk veya sekme içinde bir seçenek belirtimine izin verilir. Komut satırı seçeneği belirtimlerine ayırmak için bir veya daha fazla boşluk veya sekme kullanın. Seçenek adları ve anahtar sözcük bağımsız değişkenleri veya dosya adı bağımsız değişkenler büyük küçük harfe duyarlı değildir. Örneğin, - bağlama ve/Bind için de aynı anlama gelir.

EDITBIN şu seçeneklere sahiptir:

|Seçenek|Amaç|
|------------|-------------|
|[/ALLOWBIND](../../build/reference/allowbind.md)|DLL'in bağlı olamayacağını belirtir.|
|[/ALLOWISOLATION](../../build/reference/allowisolation.md)|DLL veya yürütülebilir dosya bildirim arama davranışını belirtir.|
|[/APPCONTAINER](../../build/reference/appcontainer.md)|Uygulamanın bir AppContainer içinde çalışmasının gerekip gerekmediğini belirtir; örneğin, bir UWP uygulaması.|
|[/BIND](../../build/reference/bind.md)|Giriş noktaları için adresleri belirtilen nesnelerin yükleme süresini hızlandırmak için ayarlar.|
|[/DYNAMICBASE](../../build/reference/dynamicbase.md)|DLL veya yürütülebilir görüntü rastgele yükleme zamanında rastgele adres alanı düzenini (ASLR) temellendirilebilen olup olmadığını belirtir.|
|[/ ERRORREPORT](../../build/reference/errorreport-editbin-exe.md)|İç hatalarını Microsoft'a bildirir.|
|[/HEAP](../../build/reference/heap.md)|Yürütülebilir resmin yığın boyutunu bayt cinsinden ayarlar.|
|[/HIGHENTROPYVA](../../build/reference/highentropyva.md)|DLL veya yürütülebilir resmin yüksek entropi (64-bit) rastgele adres alanı düzenini (ASLR) destekleyip desteklemediğini belirtir.|
|[/INTEGRITYCHECK](../../build/reference/integritycheck.md)|Yükleme zamanında dijital imza denetlenip denetlenmeyeceğini belirtir.|
|[/LARGEADDRESSAWARE](../../build/reference/largeaddressaware.md)|Nesne iki gigabayttan büyük adresleri destekleyip desteklemediğini belirtir.|
|[/ NOLOGO](../../build/reference/nologo-editbin.md)|EDITBIN Başlangıç başlığını göstermez.|
|[/NXCOMPAT](../../build/reference/nxcompat.md)|Yürütülebilir resmin Windows veri yürütme önlemesi ile uyumlu olup olmadığını belirtir.|
|[/REBASE](../../build/reference/rebase.md)|Belirtilen nesneler için temel adres ayarlar.|
|[/RELEASE](../../build/reference/release.md)|Üst bilgisinde sağlama toplamını ayarlar.|
|[/ SECTION](../../build/reference/section-editbin.md)|Bir bölümün özniteliklerini geçersiz kılar.|
|[/STACK](../../build/reference/stack.md)|Yürütülebilir resmin yığın boyutunu bayt cinsinden ayarlar.|
|[/SUBSYSTEM](../../build/reference/subsystem.md)|Yürütme ortamını belirtir.|
|[/SWAPRUN](../../build/reference/swaprun.md)|Yürütülebilir resmin gerekir takas dosyasına kopyalanır ve ardından oradan çalıştırın belirtir.|
|[/TSAWARE](../../build/reference/tsaware.md)|Uygulama, çok kullanıcılı ortamda çalıştırmak için tasarlanmıştır belirtir.|
|[/VERSION](../../build/reference/version.md)|Üst bilgisinde sürüm numarasını ayarlar.|

## <a name="see-also"></a>Ayrıca Bkz.

[C/C++ Derleme Araçları](../../build/reference/c-cpp-build-tools.md)<br/>
[EDITBIN Başvurusu](../../build/reference/editbin-reference.md)