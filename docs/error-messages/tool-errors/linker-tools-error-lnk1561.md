---
title: Bağlayıcı araçları hatası LNK1561 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1561
dev_langs:
- C++
helpviewer_keywords:
- LNK1561
ms.assetid: cb0b709b-7c9c-4496-8a4e-9e1e4aefe447
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8de3a8eebb8cc023f3ee6f2d2e4c82e718fe79e7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="linker-tools-error-lnk1561"></a>Bağlayıcı Araçları Hatası LNK1561
Giriş noktası tanımlanmalıdır  
  
Bağlayıcı öğenizi bulamadınız bir *giriş noktası*, yürütülebilir dosya çağırmak için başlangıç işlevi. Varsayılan olarak, bağlayıcı arar bir `main` veya `wmain` işlevi bir konsol uygulaması için bir `WinMain` veya `wWinMain` işlevi için bir Windows uygulaması veya `DllMain` başlatma gerektiren bir DLL için. Başka bir işlevi kullanarak belirtebilirsiniz [/Entry](../../build/reference/entry-entry-point-symbol.md) bağlayıcı seçeneği.  
  
Bu hatanın birkaç nedeni olabilir:  
-   Giriş noktası bağlamak için dosya listesinde tanımlayan dosyası dahil. Giriş noktası işlevi içeren dosyayı uygulamanıza bağlandığını doğrulayın.  
-   Yanlış işlev imzası kullanarak giriş noktası tanımlanmış; Örneğin, yanlış yazıldığında veya yanlış durumda işlevi adı için kullanılan veya olabilirsiniz dönüş türü veya parametre türleri hatalı şekilde belirtildi.  
-   Değil belirtmiş olabilirsiniz [/dll](../../build/reference/dll-build-a-dll.md) DLL oluştururken seçeneği.  
-   Kullandığınız zaman, giriş noktası işlevi adı yanlış belirtmiş olabilirsiniz [/Entry](../../build/reference/entry-entry-point-symbol.md) bağlayıcı seçeneği.  
-   Kullanıyorsanız [LIB](../../build/reference/lib-reference.md) DLL oluşturmak için aracı, .def dosyası belirtmiş olabilirsiniz. Bu durumda, .def dosyası derlemeden kaldırın.    
  
Bir uygulama oluştururken, bağlayıcı kodunuzu başlatmak için çağırmak bir giriş noktası işlevi için arar. Bu uygulama yüklenir ve çalışma zamanı başlatıldı sonra çağrılan işlevdir. Bir uygulama için bir giriş noktası işlevi sağlamanız gerekir veya uygulamanızın çalışamaz. Bir giriş noktası bir DLL için isteğe bağlıdır. Varsayılan olarak, bağlayıcı gibi birkaç belirli adları ve imzalar, biri olan bir giriş noktası işlevi için görünür `int main(int, char**)`. Başka bir işlev adı girişi olarak belirtebilirsiniz/Entry bağlayıcı seçeneği kullanılarak noktası.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek LNK1561 oluşturur:  
  
```cpp  
// LNK1561.cpp  
// LNK1561 expected  
int i;  
// add a main function to resolve this error  
```