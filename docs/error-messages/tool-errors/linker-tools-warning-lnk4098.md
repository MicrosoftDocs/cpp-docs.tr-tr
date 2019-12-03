---
title: Bağlayıcı Araçları Uyarısı LNK4098
description: Uyumsuz kitaplıkların bağlayıcı araçları uyarısı LNK4098 neden olmasının yanı sıra/NODEFAULTLIB 'i onarmak için nasıl kullanılacağı açıklanmaktadır.
ms.date: 12/02/2019
f1_keywords:
- LNK4098
helpviewer_keywords:
- LNK4098
ms.assetid: 1f1b1408-1316-4e34-80f5-6a02f2db0ac1
ms.openlocfilehash: 9d0c7da0614651a98d5ed4f3bd3676c7d837ce67
ms.sourcegitcommit: d0504e2337bb671e78ec6dd1c7b05d89e7adf6a7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/02/2019
ms.locfileid: "74682937"
---
# <a name="linker-tools-warning-lnk4098"></a>Bağlayıcı Araçları Uyarısı LNK4098

> defaultlib '*Library*' diğer kitaplıkların kullanımıyla çakışıyor; /NODEFAULTLıB:*Library* kullanın

Uyumsuz kitaplıklarla bağlantı kurmaya çalışıyorsunuz.

> [!NOTE]
> Çalışma zamanı kitaplıkları artık farklı türleri karıştırmaya engel olan yönergeler içeriyor. Aynı programda farklı türler veya hata ayıklama ve hata ayıklama olmayan sürümlerini kullanmayı denerseniz bu uyarıyı alırsınız. Örneğin, bir dosyayı farklı bir tür (örneğin, hata ayıklama ve perakende) kullanmak için tek bir çalışma zamanı kitaplığı ve başka bir dosya kullanmak üzere derlemişse, bu uyarıyı alırsınız. Tüm kaynak dosyalarını aynı çalışma zamanı kitaplığını kullanacak şekilde derlemeniz gerekir. Daha fazla bilgi için bkz. [/MD,/MT,/LD (çalışma zamanı kitaplığı kullanın)](../../build/reference/md-mt-ld-use-run-time-library.md) derleyici seçenekleri.

Bağlayıcının hangi kitaplıkların arayacağını bulmak için bağlayıcının [/verbose: LIB](../../build/reference/verbose-print-progress-messages.md) anahtarını kullanabilirsiniz. Örneğin, çalıştırılabilir, çok iş parçacıklı, hata ayıklama olmayan çalışma zamanı kitaplıklarını kullandığında, bildirilen liste LIBCMT. lib ve LIBCMTD. lib, MSVCRT. lib veya MSVCRTD. lib içermemelidir. Bağlayıcıyı, yok saymak istediğiniz her kitaplık için [/nodefaultlib](../../build/reference/nodefaultlib-ignore-libraries.md) kullanarak yanlış çalışma zamanı kitaplıklarını yoksayacak şekilde söyleyebilirsiniz.

Aşağıdaki tabloda hangi kitaplıkların hangi çalışma zamanı kitaplığına bağlı olarak yoksayılması gerektiğini gösterilmektedir. Komut satırında, her bir kitaplık için yoksayılacak bir **/nodefaultlib** seçeneği kullanın. Visual Studio IDE 'de, **belirli varsayılan kitaplıkları Yoksay** özelliğindeki kitaplıkları noktalı virgülle ayırarak yok saymaya ayırın.

| Bu çalışma zamanı kitaplığını kullanmak için | Bu kitaplıkları Yoksay |
|-----------------------------------|----------------------------|
| Çok iş parçacıklı (Libcmt. lib) | Msvcrt. lib; libcmtd. lib; msvcrtd. lib |
| DLL kullanarak çok iş parçacıklı (Msvcrt. lib) | Libcmt. lib; libcmtd. lib; msvcrtd. lib |
| Çok Iş parçacıklı hata ayıklama (libcmtd. lib) | Libcmt. lib; Msvcrt. lib; msvcrtd. lib |
| DLL kullanarak çok Iş parçacıklı hata ayıklama (msvcrtd. lib) | Libcmt. lib; Msvcrt. lib; libcmtd. lib |

Örneğin, bu uyarıyı aldıysanız ve çalışma zamanı kitaplıklarının hata ayıklama olmayan DLL sürümünü kullanan yürütülebilir bir dosya oluşturmak istiyorsanız bağlayıcı ile aşağıdaki seçenekleri kullanabilirsiniz:

```cmd
/NODEFAULTLIB:libcmt.lib /NODEFAULTLIB:libcmtd.lib /NODEFAULTLIB:msvcrtd.lib
```
