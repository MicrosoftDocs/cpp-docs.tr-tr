---
title: "EDITBIN seçenekleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: editbin
dev_langs: C++
helpviewer_keywords: EDITBIN program, options
ms.assetid: 2da9f88e-cbab-4d64-bb66-ef700535230f
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 5a4b30b5fdc3294220b210001cc19a58bdf4b3b3
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="editbin-options"></a>EDITBIN Seçenekleri
Nesne dosyaları, yürütülebilir dosyaları ve dinamik bağlantı kitaplıklarını (DLL'ler) değiştirmek için EDITBIN kullanabilirsiniz. EDITBIN yaptığı değişiklikler seçeneklerini belirtin.  
  
 İsteğe bağlı bir tire (-) ya da seçenek adında eğik çizgi (/), bir seçenek belirticisi oluşur. Seçenek adları kısaltılmış olamaz. Bazı seçenekler iki nokta (:) sonra belirtilen bağımsız değişkenler almayan. Hiçbir boşluk ya da sekme bir seçenek belirtimi içinde izin verilir. Komut satırı seçeneği belirtimlere ayırmak için bir veya daha fazla boşluk ya da sekme kullanın. Seçenek adları ve anahtar sözcüğü bağımsız veya dosya adı bağımsız büyük küçük harfe duyarlı değildir. Örneğin, - BIND ve/Bind için aynı anlama gelir.  
  
 EDITBIN aşağıdaki seçenekler vardır:  
  
|Seçenek|Amaç|  
|------------|-------------|  
|[/ ALLOWBIND](../../build/reference/allowbind.md)|DLL bağlı olup olmadığını belirtir.|  
|[/ ALLOWISOLATION](../../build/reference/allowisolation.md)|DLL veya yürütülebilir dosya bildirim arama davranışını belirtir.|  
|[/ APPCONTAINER](../../build/reference/appcontainer.md)|Uygulama içinde bir Appcontaıner çalıştırma olup olmadığını belirtir; örneğin, bir [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] uygulama.|  
|[/ BIND](../../build/reference/bind.md)|Giriş noktaları için adresleri yükleme süresini hızlandırmak için belirtilen nesneler ayarlar.|  
|[/ DYNAMICBASE](../../build/reference/dynamicbase.md)|DLL veya yürütülebilir görüntü rastgele yükleme zamanında adres boşluğu düzeni rastgele seçimini (ASLR) kullanarak rebased olup olmadığını belirtir.|  
|[/ ERRORREPORT](../../build/reference/errorreport-editbin-exe.md)|İç hataları Microsoft'a bildirir.|  
|[/ HEAP](../../build/reference/heap.md)|Yürütülebilir görüntünün öbek boyutunu bayt cinsinden ayarlar.|  
|[/ HIGHENTROPYVA](../../build/reference/highentropyva.md)|DLL veya yürütülebilir görüntü yüksek entropi (64-bit) adres boşluğu düzeni rastgele seçimini (ASLR) destekleyip desteklemediğini belirtir.|  
|[/ INTEGRITYCHECK](../../build/reference/integritycheck.md)|Yükleme zamanında dijital imza denetlenip denetlenmeyeceğini belirtir.|  
|[/ LARGEADDRESSAWARE](../../build/reference/largeaddressaware.md)|Nesne iki gigabayttan büyük adresleri destekleyip desteklemediğini belirtir.|  
|[/ NOLOGO](../../build/reference/nologo-editbin.md)|EDITBIN Başlangıç başlığını gizler.|  
|[/ NXCOMPAT](../../build/reference/nxcompat.md)|Yürütülebilir görüntü Windows Veri Yürütme Engellemesi ile uyumlu olup olmadığını belirtir.|  
|[/ REBASE](../../build/reference/rebase.md)|Belirtilen nesneler için temel adres ayarlar.|  
|[/ RELEASE](../../build/reference/release.md)|Sağlama toplamı üstbilgisinde ayarlar.|  
|[/ SECTION](../../build/reference/section-editbin.md)|Bir bölüm özniteliklerini geçersiz kılar.|  
|[/ STACK](../../build/reference/stack.md)|Yürütülebilir görüntünün yığın boyutunu bayt cinsinden ayarlar.|  
|[/ SUBSYSTEM](../../build/reference/subsystem.md)|Yürütme ortamı belirtir.|  
|[/ SWAPRUN](../../build/reference/swaprun.md)|Yürütülebilir görüntü gerekir olarak takas dosyasına kopyalanır ve buradan çalıştırın olduğunu belirtir.|  
|[/ TSAWARE](../../build/reference/tsaware.md)|Uygulama çok kullanıcılı ortamda çalışmak üzere tasarlanmıştır belirtir.|  
|[/ SÜRÜMÜ](../../build/reference/version.md)|Sürüm numarasını üstbilgisinde ayarlar.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C/C++ derleme araçları](../../build/reference/c-cpp-build-tools.md)   
 [EDITBIN başvurusu](../../build/reference/editbin-reference.md)