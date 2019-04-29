---
title: '/ ZC: threadsafeınit (iş parçacığı güvenli yerel statik başlatma)'
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
ms.openlocfilehash: 92a1bfa5ec3bab2814397d51e35e617b7666c706
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62315709"
---
# <a name="zcthreadsafeinit-thread-safe-local-static-initialization"></a>/ ZC: threadsafeınit (iş parçacığı güvenli yerel statik başlatma)

**/ZC: threadsafeınit** derleyici seçeneği, el ile eşitleme gereği ortadan kaldırılır iş parçacığı güvenli bir şekilde, statik yerel (işlev kapsamı) değişkenleri başlatmak için derleyicinin söyler. Yalnızca başlatma, iş parçacığı açısından güvenlidir. Kullanım ve statik yerel değişkenlerin birden çok iş parçacığı tarafından değiştirilmesini el ile eşitlenmesi gerekir. Bu seçenek, Visual Studio 2015'ten başlayarak kullanılabilir. Varsayılan olarak, Visual Studio bu seçeneği etkinleştirir.

## <a name="syntax"></a>Sözdizimi

> **/Zc:threadSafeInit**[**-**]

## <a name="remarks"></a>Açıklamalar

C ++ 11'de standart blok kapsamı statik değişkenlerle veya iş parçacığı depolama süresi sıfır-başka bir başlatma gerçekleşmeden önce başlatılması gerekir. Başlatma denetimi değişkenin bildirimi ilk başarılı olduğunda gerçekleşir. Başlatma sırasında bir özel durum, değişken başlatılmamış olarak kabul edilir ve başlatma yeniden denemesi, sonraki zaman denetim bildirimi geçirir. Denetim bildirimi başlatma, eş zamanlı yürütme taşları başlatma tamamlanırken eşzamanlı girerse. Yeniden başlatma sırasında denetim bildirimi yinelemeli olarak girer, tanımsız bir davranıştır. Varsayılan olarak, Visual Studio Visual Studio 2015'ten başlayarak, bu standart davranışı uygular. Bu davranışı açıkça ayarlayarak belirtilebilir **/ZC: threadsafeınit** derleyici seçeneği.

**/ZC: threadsafeınit** derleyici seçeneği varsayılan olarak açıktır. [/ Permissive-](permissive-standards-conformance.md) seçeneği etkilemez **/ZC: threadsafeınit**.

İş parçacığı açısından güvenli başlatma statik yerel değişkenlerin Evrensel C Çalışma Zamanı Kitaplığı'nda (UCRT) uygulanan kod kullanır. UCRT üzerinde bir bağımlılık alma önlemek ve Visual Studio'nun önceki Visual Studio 2015 sürümlerini iş parçacığı güvenli başlatma davranışı korumak için kullanmak **/ZC: threadsafeınit** seçeneği. Bu iş parçacığı güvenliği gerekli olmadığını biliyorsanız, statik yerel bildirimleri etrafında biraz daha küçük, daha hızlı kod oluşturmak için bu seçeneği kullanın.

İş parçacığı güvenli statik yerel değişkenler iş parçacığı yerel depolama (TLS) statik zaten başlatılmış, etkili çalıştırma sağlamak için dahili olarak kullanın. Bu özellik uygulamasını Windows Vista ve sonraki işletim sistemlerinde Windows işletim sistemi desteği işlevlerini kullanır. Verimliliği avantajı elde ederim için Windows XP, Windows Server 2003 ve önceki işletim sistemleri bu destek yok. Bu işletim sistemlerini, daha düşük bir sınır yüklenebilen TLS bölüm sayısına de sahip. Bölüm sınırı aşan TLS kilitlenmeye neden olabilir. Bu, özellikle daha eski işletim sistemlerinde çalışması gereken kod kodunuzda bir sorun ise kullanın **/ZC: threadsafeınit** iş parçacığı açısından güvenli başlatma kodu devre dışı bırakmak için.

Visual C++'ta uyumluluk sorunları hakkında daha fazla bilgi için bkz: [standart dışı davranış](../../cpp/nonstandard-behavior.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Gelen **yapılandırmaları** açılır menü öğesini **yapılandırmalarında**.

1. Seçin **yapılandırma özellikleri** > **C/C++** > **komut satırı** özellik sayfası.

1. Değiştirme **ek seçenekler** eklenecek özellik **/ZC: threadsafeınit** veya **/ZC: threadsafeınit** seçip **Tamam**.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC Derleyicisi Seçenekleri](compiler-options.md)<br/>
[MSVC Derleyicisi Komut Satırı Söz Dizimi](compiler-command-line-syntax.md)<br/>
[/Zc (Uyumluluk)](zc-conformance.md)<br/>
