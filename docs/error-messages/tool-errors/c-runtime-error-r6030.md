---
title: C çalışma zamanı hatası R6030 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- R6030
dev_langs:
- C++
helpviewer_keywords:
- R6030
ms.assetid: 0238a6c3-a033-4046-8adc-f8f99d961153
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 63606624e1cbcc5ef2c5ea453ee6d346e3e686a8
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46038132"
---
# <a name="c-runtime-error-r6030"></a>C çalışma zamanı hatası R6030

CRT başlatılmadı

> [!NOTE]
>  Bir uygulama çalıştırırken bu hatayla karşılaşırsanız, dahili bir sorun olduğundan uygulaması kapatıldı. Bu sorun genellikle belirli güvenlik yazılım programları veya nadiren de olsa bir programın hata neden olur.
>
>  Bu hatayı düzeltmek için aşağıdaki adımları deneyebilirsiniz:
>
>  -   Bu sorunu giderme için yönergeler güvenlik yazılımının olabilir. Ayrıntılar için güvenlik yazılım satıcısının Web sitesine bakın. Alternatif olarak, güvenlik yazılımının güncelleştirilmiş sürümlerini denetlemek ya da farklı güvenlik yazılımı deneyin.
> -   Kullanım **uygulamalar ve Özellikler** veya **programlar ve Özellikler** sayfasını **Denetim Masası** onarın veya programı yeniden yükleyin.
> -   Denetleme **Windows Update** içinde **Denetim Masası** yazılım güncelleştirmeleri için.
> -   Uygulamanın güncelleştirilmiş bir sürümünü denetleyin. Sorun devam ederse uygulama satıcısına başvurun.

**Programcıları için bilgi**

C çalışma zamanı (CRT) kullanıyorsanız, ancak CRT başlatma kodunu yürütülmedi bu hata oluşur. Bağlayıcı geçiş yaparsanız, bu hatayı almak olası [/Entry](../../build/reference/entry-entry-point-symbol.md) başlangıç adresi, genellikle varsayılan geçersiz kılmak için kullanılan **mainCRTStartup**, **wmainCRTStartup** için bir Konsol EXE **WinMainCRTStartup** veya **wWinMainCRTStartup** için bir Windows EXE veya **_DllMainCRTStartup** bir DLL için. Yukarıdaki işlevlerden birini başlangıç olarak adlandırılan sürece, C çalışma zamanı başlatılmayacak. C Çalışma Zamanı Kitaplığı'na bağlamak ve normal kullandığınızda varsayılan olarak bu başlangıç İşlevler normalde çağrılır **ana**, **wmain**, **WinMain**, veya  **DllMain** giriş noktaları.

Başka bir program, bazı DLL Kitaplığı çağrıları yakalamak için kod ekleme teknikleri kullanır. Bu hatayı almak mümkündür. Bazı müdahale eden güvenlik programlarını bu tekniği kullanın. Önce Visual Studio 2015 Visual C++ sürümlerinde, sorunu gidermek için bir statik olarak bağlanan CRT kitaplığı kullanmak da mümkündür, ancak bu güvenlik ve uygulama güncelleştirmelerini nedenleriyle önerilmez. Bu sorunu düzeltmek için son kullanıcı eylem gerektirebilir.