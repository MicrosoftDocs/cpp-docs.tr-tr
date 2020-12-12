---
description: 'Şu konuda daha fazla bilgi edinin:/Zc: threadSafeInit (Iş parçacığı güvenli yerel statik başlatma)'
title: '/Zc: threadSafeInit (Iş parçacığı güvenli yerel statik başlatma)'
ms.date: 03/14/2018
f1_keywords:
- threadSafeInit
- /Zc:threadSafeInit
helpviewer_keywords:
- -Zc compiler options (C++)
- threadSafeInit
- Thread-safe Local Static Initialization
- /Zc compiler options (C++)
- Zc compiler options (C++)
ms.assetid: a0fc4b34-2cf0-45a7-a642-b8afc4ca19f2
ms.openlocfilehash: ac14e7979d2adab0b21229f426e00a489c14f38f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97271219"
---
# <a name="zcthreadsafeinit-thread-safe-local-static-initialization"></a>/Zc: threadSafeInit (Iş parçacığı güvenli yerel statik başlatma)

**/Zc: threadSafeInit** derleyici seçeneği derleyiciye statik yerel (işlev kapsamı) değişkenlerini iş parçacığı açısından güvenli bir şekilde başlatmasını söyler, el ile eşitleme gereksinimini ortadan kaldırır. Yalnızca başlatma iş parçacığı güvenlidir. Statik yerel değişkenlerin birden fazla iş parçacığı tarafından kullanılması ve değiştirilmesi hala el ile eşitlenmelidir. Bu seçenek, Visual Studio 2015 ' den itibaren kullanılabilir. Varsayılan olarak, Visual Studio bu seçeneği sunar.

## <a name="syntax"></a>Syntax

> **/Zc: threadSafeInit**[ **-** ]

## <a name="remarks"></a>Açıklamalar

C++ 11 standardında, diğer bir başlatma gerçekleşmeden önce statik veya iş parçacığı depolama süresine sahip blok kapsam değişkenleri sıfır olarak başlatılmış olmalıdır. Başlatma, denetimin ilk olarak değişkenin bildirimiyle geçtiğinde oluşur. Başlatma sırasında bir özel durum oluşursa, değişken başlatılmamış olarak kabul edilir ve denetim bildirimden bir sonraki sefer geçtiğinde başlatma yeniden denenir. Denetim, bildirimi başlatma ile aynı anda girerse, başlatma sırasında eşzamanlı yürütme blokları tamamlanır. Denetim, başlatma sırasında bildirime özyinelemeli olarak yeniden girerse davranış tanımsızdır. Varsayılan olarak, Visual Studio 2015 ' den başlayarak Visual Studio bu standart davranışı uygular. Bu davranış, **/Zc: threadSafeInit** derleyici seçeneği ayarlanarak açıkça belirtilebilir.

**/Zc: threadSafeInit** derleyici seçeneği varsayılan olarak açık. [/Permissive-](permissive-standards-conformance.md) seçeneği **/Zc: threadSafeInit**' i etkilemez.

Statik yerel değişkenlerin iş parçacığı güvenli başlatması, evrensel C çalışma zamanı kitaplığı 'nda (UCRT) uygulanan koda dayanır. UıCRT üzerinde bir bağımlılık oluşmaması veya Visual Studio 2015 öncesi Visual Studio sürümlerinin iş parçacığı güvenli olmayan başlatma davranışını korumak için **/Zc: threadSafeInit-** seçeneğini kullanın. İş parçacığı güvenliği gerekmediğini biliyorsanız, statik yerel bildirimler etrafında biraz daha küçük, daha hızlı kod oluşturmak için bu seçeneği kullanın.

İş parçacığı açısından güvenli statik yerel değişkenler, statik olarak zaten başlatılmış olduğunda verimli bir yürütme sağlamak için iş parçacığı yerel depolaması (TLS) kullanır. Bu özelliğin uygulanması Windows Vista ve sonraki işletim sistemlerinde Windows işletim sistemi destek işlevlerine bağımlıdır. Windows XP, Windows Server 2003 ve daha eski işletim sistemlerinde bu destek yoktur, bu nedenle verimlilik avantajına sahip değildir. Bu işletim sistemlerinin Ayrıca, yüklenebilen TLS bölümlerinin sayısına daha düşük bir sınırı vardır. TLS bölümü sınırının aşılması kilitlenmeye neden olabilir. Kodunuzda bir sorun olması halinde, özellikle eski işletim sistemlerinde çalışması gereken kodda, iş parçacığı güvenli başlatma kodunu devre dışı bırakmak için **/Zc: threadSafeInit-** kullanın.

Visual C++ uyumluluk sorunları hakkında daha fazla bilgi için bkz. [Standart olmayan davranış](../../cpp/nonstandard-behavior.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Konfigürasyonlar** açılan menüsünde **Tüm Konfigürasyonlar**' ı seçin.

1. **Yapılandırma özellikleri**  >  **C/C++**  >  **komut satırı** Özellik sayfası ' nı seçin.

1. **Ek seçenekler** özelliğini **/Zc: threadSafeInit** veya **/Zc: threadSafeInit-** içerecek şekilde değiştirin ve ardından **Tamam**' ı seçin.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici Command-Line sözdizimi](compiler-command-line-syntax.md)<br/>
[/Zc (Uyumluluk)](zc-conformance.md)<br/>
