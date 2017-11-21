---
title: "Bağlayıcı araçları hatası LNK1561 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK1561
dev_langs: C++
helpviewer_keywords: LNK1561
ms.assetid: cb0b709b-7c9c-4496-8a4e-9e1e4aefe447
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: b3a6ad889969292a65afb7b363412eaf7d7a6430
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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