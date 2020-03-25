---
title: C Çalışma Zamanı Hatası R6030
ms.date: 11/04/2016
f1_keywords:
- R6030
helpviewer_keywords:
- R6030
ms.assetid: 0238a6c3-a033-4046-8adc-f8f99d961153
ms.openlocfilehash: 5d7160623d4e1eb83240c09e637c780fefc0d43d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80197125"
---
# <a name="c-runtime-error-r6030"></a>C Çalışma Zamanı Hatası R6030

CRT başlatılmadı

> [!NOTE]
> Bir uygulamayı çalıştırırken bu hata iletisiyle karşılaşırsanız, bir iç sorun olduğundan uygulama kapatıldı. Bu sorun genellikle belirli güvenlik yazılımı programlarından veya nadiren, programdaki bir hata nedeniyle oluşur.
>
> Bu hatayı düzeltmek için aşağıdaki adımları deneyebilirsiniz:
>
> - Güvenlik yazılımınız bu sorunu azaltmaya yönelik belirli yönergelere sahip olabilir. Ayrıntılar için güvenlik yazılımı satıcınızın Web sitesine bakın. Alternatif olarak, güvenlik yazılımınızın güncelleştirilmiş sürümlerini denetleyin veya farklı güvenlik yazılımlarını deneyin.
> - Programı onarmak ya da yeniden yüklemek için **Denetim Masası** 'ndaki **uygulamalar ve Özellikler** veya **Programlar ve Özellikler** sayfasını kullanın.
> - Yazılım güncelleştirmeleri için **Denetim Masası** 'ndaki **Windows Update** kontrol edin.
> - Uygulamanın güncelleştirilmiş bir sürümünü denetleyin. Sorun devam ederse uygulama satıcısına başvurun.

**Programcılar için bilgiler**

Bu hata, C çalışma zamanı (CRT) kullanıyorsanız oluşur, ancak CRT başlangıç kodu yürütülmedi. Varsayılan başlangıç adresini (genellikle **mainCRTStartup**, BIR konsol exe için **wmainCRTStartup** , bir Windows exe Için **WinMainCRTStartup** veya **wwinmaincrtstartup** veya bir dll için **_DllMainCRTStartup** geçersiz kılmak için kullanılan bağlayıcı anahtarı [/Entry](../../build/reference/entry-entry-point-symbol.md) kullanılırsa bu hatayı almak mümkündür. Yukarıdaki işlevlerden biri başlangıçta çağrılmamışsa, C çalışma zamanı başlatılmayacak. Bu başlangıç işlevleri genellikle C çalışma zamanı kitaplığı ' na bağlantı oluşturduğunuzda ve normal **Main**, **wmain**, **wınmain**veya **DllMain** giriş noktalarını kullandığınızda varsayılan olarak çağrılır.

Başka bir program belirli DLL kitaplığı çağrılarını yakalamak için kod ekleme tekniklerini kullandığında bu hatayı almak da mümkündür. Bazı güvenlik programları bu tekniği kullanır. Visual Studio 2015 ' C++ den önceki Visual sürümlerinde, sorunu gidermek için statik olarak BAĞLANMıŞ bir CRT kitaplığı kullanmak mümkündür, ancak bu, güvenlik ve uygulama güncelleştirmelerinin nedenleri için önerilmez. Bu sorunu düzeltmek için son kullanıcı eylemi gerekebilir.
