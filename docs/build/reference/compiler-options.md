---
title: "Derleyici Seçenekleri | Microsoft Docs"
ms.custom: 
ms.date: 01/29/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- cl.exe compiler
- x86 Visual C++ compiler
- ARM Visual C++ compiler
- compiler options, C++
- x64 Visual C++ compiler
ms.assetid: ed3376c8-bef4-4c9a-80e9-3b5da232644c
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4addd9f5dce819f554e6ab04707929a32f7b7d9d
ms.sourcegitcommit: 30ab99c775d99371ed22d1a46598e542012ed8c6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/03/2018
---
# <a name="compiler-options"></a>Derleyici Seçenekleri

cl.exe Microsoft Visual C++ (MSVC) C ve C++ Derleyicileri ve bağlayıcı denetleyen bir araçtır. cl.exe yalnızca Microsoft Windows için Visual Studio desteklendiği işletim sistemlerinin üzerinde çalıştırılabilir.

> [!NOTE]  
> Bu araç yalnızca Visual Studio Geliştirici komut isteminden başlatabilirsiniz. Bir sistem komut istemi veya dosya Gezgini başlatılamıyor. Daha fazla bilgi için bkz: [komut satırında C/C++ derleme kodu](../building-on-the-command-line.md).

Derleyicileri ortak nesne dosyası biçimi (COFF) nesne (.obj) dosyaları üretir. Bağlayıcı yürütülebilir dosyanın (.exe) dosyaları veya dinamik bağlantı kitaplıklarını (DLL'ler) oluşturur.

Tüm derleyici seçenekleri büyük küçük harfe duyarlı olduğunu unutmayın. Her iki eğik kullanabilir (`/`) veya bir tire (`-`) derleyici seçeneği belirtmek için.

Bağlantılandırmadan derleme için kullanmak [/c](../../build/reference/c-compile-without-linking.md) seçeneği.

## <a name="find-a-compiler-option"></a>Derleyici seçeneği Bul

Belirli derleyici seçeneği bulmak için aşağıdaki listede birine bakın:

- [Alfabetik Listelenmiş Derleyici Seçenekleri](../../build/reference/compiler-options-listed-alphabetically.md)

- [Kategorilere Göre Listelenen Derleyici Seçenekleri](../../build/reference/compiler-options-listed-by-category.md)

## <a name="specify-compiler-options"></a>Derleyici seçeneklerini belirtin

Her derleyici seçeneği konuda geliştirme ortamında nasıl ayarlanabilir anlatılmaktadır. Geliştirme ortamı dışında seçeneklerini belirtme hakkında daha fazla bilgi için bkz:

- [Derleyici Komut Satırı Sözdizimi](../../build/reference/compiler-command-line-syntax.md)

- [CL Komut Dosyaları](../../build/reference/cl-command-files.md)

- [CL Ortam Değişkenleri](../../build/reference/cl-environment-variables.md)

## <a name="related-build-tools"></a>İlgili derleme araçları

[Bağlayıcı seçenekleri](../../build/reference/linker-options.md) programınızı nasıl yapılandırıldığını de etkiler.

## <a name="see-also"></a>Ayrıca bkz.

[C/C++ Derleme Başvurusu](../../build/reference/c-cpp-building-reference.md)  
[Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)  
[Hızlı Derleme](../../build/reference/fast-compilation.md)  
[CL Bağlayıcı Çağırır](../../build/reference/cl-invokes-the-linker.md)  
