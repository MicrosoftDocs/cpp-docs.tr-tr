---
title: /ZC:threadSafeInit (iş parçacığı yerel statik başlatma) | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- threadSafeInit
- /Zc:threadSafeInit
dev_langs:
- C++
helpviewer_keywords:
- -Zc compiler options (C++)
- threadSafeInit
- Thread-safe Local Static Initialization
- /Zc compiler options (C++)
- Zc compiler options (C++)
ms.assetid: a0fc4b34-2cf0-45a7-a642-b8afc4ca19f2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 438ce5ba783f646e9c8e61d9b82999ea936532b4
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="zcthreadsafeinit-thread-safe-local-static-initialization"></a>/ZC:threadSafeInit (iş parçacığı yerel statik başlatma)

**/Zc:threadSafeInit** derleyici seçeneği statik yerel (işlev kapsamı) değişkenleri el ile eşitleme gereksinimini bir iş parçacığı açısından güvenli şekilde başlatmak için derleyici söyler. Yalnızca başlatma iş parçacığı güvenlidir. Kullanım ve statik yerel değişkenler birden çok iş parçacığı tarafından değiştirilmesini hala el ile eşitlenmelidir. Bu seçenek, Visual Studio 2015'ten başlayarak kullanılabilir. Varsayılan olarak, Visual Studio bu seçeneği etkinleştirir.

## <a name="syntax"></a>Sözdizimi

> **/Zc:threadSafeInit**[**-**]

## <a name="remarks"></a>Açıklamalar

C ++ 11'de standart blok kapsamı statik değişkenlerle veya iş parçacığı depolama süresi sıfır-diğer başlatma gerçekleşmeden önce başlatılması gerekir. Denetim ilk değişken bildirimi geçerken başlatma gerçekleşir. Başlatma sırasında bir özel durum, değişkeni başlatılmadı olarak kabul edilir ve başlatma yeniden denemesi ise sonraki zamanı denetimi bildirimi geçirir. Denetim bildirimi eşzamanlı olarak başlatma, başlatma tamamlanırken eş zamanlı yürütme blokları girerse. Denetim bildirimi yinelemeli olarak başlatma sırasında yeniden girerse tanımlanmamış bir davranıştır. Varsayılan olarak, Visual Studio 2015'ten başlayarak Visual Studio bu standart davranışı uygular. Bu davranış açıkça ayarlayarak belirtilebilir **/Zc:threadSafeInit** derleyici seçeneği.

**/Zc:threadSafeInit** derleyici seçeneği varsayılan olarak açıktır. [/ İzin veren-](permissive-standards-conformance.md) seçeneği etkilemez **/Zc:threadSafeInit**.

Evrensel C Çalışma Zamanı Kitaplığı'nda (UCRT) uygulanan kod parçacığı başlatma statik yerel değişkenleri kullanır. Bir bağımlılık üzerinde UCRT almaktan kaçının ya da Visual Studio 2015 önce Visual Studio sürümleri iş parçacığı güvenli başlatma davranışını korumak için kullanmak **/Zc:threadSafeInit-** seçeneği. Bu iş parçacığı güvenliği gerekli olmadığını biliyorsanız, statik yerel bildirimler geçici biraz daha küçük, daha hızlı kodu oluşturmak için bu seçeneği kullanın.

İş parçacığı statik yerel değişkenler iş parçacığı yerel depolaması (TLS) statik zaten başlatılmış olan verimli yürütme sağlamak için dahili olarak kullanın. Bu özellik uyarlamasını Windows Vista ve sonraki işletim sistemlerinde Windows işletim sistemi desteği işlevlerini kullanır. Böylece verimliliği avantajı elde değil Windows XP, Windows Server 2003 ve daha eski işletim sistemleri bu desteği yok. Bu işletim sistemleri daha düşük bir sınır de yüklenebilir TLS bölüm sayısına sahip. TLS aşan bir çökme bölüm sınır neden olabilir. Bu, özellikle eski işletim sistemlerinde çalıştırmalısınız kod kodunuzu bir sorun ise kullanın **/Zc:threadSafeInit-** iş parçacığı başlatma kodunu devre dışı bırakmak için.

Visual c++ uyumluluk sorunları hakkında daha fazla bilgi için bkz: [standart dışı davranış](../../cpp/nonstandard-behavior.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).

1. Gelen **yapılandırmaları** açılır menü, seçin **tüm yapılandırmaları**.

1. Seçin **yapılandırma özellikleri** > **C/C++** > **komut satırı** özellik sayfası.

1. Değiştirme **ek seçenekler** eklenecek özellik **/Zc:threadSafeInit** veya **/Zc:threadSafeInit-** ve ardından **Tamam**.

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici Seçenekleri](../../build/reference/compiler-options.md)<br/>
[Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)<br/>
[/Zc (Uyumluluk)](../../build/reference/zc-conformance.md)<br/>
