---
title: "Giriş dosyaları .netmodule biçimlerinin seçme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 4653d1bd-300f-4083-86f5-d1a06f44e61c
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a46c2fa9ce553948c03cd2ab6ad20001d0021bed
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="choosing-the-format-of-netmodule-input-files"></a>.netmodule Giriş Dosyaları Biçimini Seçme
MSIL .obj dosya (ile derlenmiş [/CLR](../../build/reference/clr-common-language-runtime-compilation.md)) .netmodule dosyası olarak da kullanılabilir.  .obj dosyaları meta verileri ve yerel simgeler içermelidir.  .netmodules yalnızca meta verileri içerir.  
  
 MSIL .obj dosya için diğer Visual Studio derleyici/addmodule derleyici seçeneği geçirin (ancak edebilirsiniz .obj dosya elde edilen derlemeyi parçası haline gelir ve derleme sevk unutmayın).  Örneğin, Visual C# ve Visual Basic/addmodule derleyici seçeneği vardır.  
  
> [!NOTE]
>  Çoğu durumda, bağlayıcıya .obj dosya .net modülünde oluşturulan derlemeden geçmesi gerekir.  Bunun tek istisnası .netmodule ile oluşturulmuşsa, [/CLR: pure](../../build/reference/clr-common-language-runtime-compilation.md).  Bir .dll veya .netmodule MSIL modülü dosyası bağlayıcıya geçirme içinde LNK1107 neden olabilir.  
  
 aracılığıyla başvuru bunların ilişkili .h dosyaları birlikte .obj dosyaları #include, .netmodule dosyasında yalnızca yönetilen türler bir C++ uygulaması tarafından kullanılabilecek ancak modülü içindeki yerel türler kullanmak C++ uygulamaları izin verin.  .Obj dosyasına geçirmeye çalışırsanız #using yerel türler hakkında bilgi; kullanılamaz # .obj dosyanın .h dosyası yerine include.  
  
 Diğer Visual Studio derleyicileri yalnızca yönetilen bir modül türlerinden kullanmasını sağlayabilirsiniz.  
  
 Visual C++ bağlayıcı modülü giriş olarak bir .netmodule veya .obj dosyası kullanmanız gerekip gerekmediğini belirlemek için aşağıdakileri kullanın:  
  
-   Visual C++ dışında bir Visual Studio derleyici ile oluşturuluyorsa, bir .netmodule oluşturabilir ve bağlayıcı giriş olarak .netmodule kullanın.  
  
-   Modüller ve modüller dışında bir kitaplığı oluşturmak için kullanılan varsa üretmek için Visual C++ derleyicisi kullanıyorsanız, bağlayıcı modülü giriş olarak derleyici tarafından üretilen .obj dosyaları kullanın; .netmodule dosya giriş olarak kullanmayın.  
  
-   Modüllerinizi yerel (olmayan bir yönetilen) kitaplığı oluşturmak için kullanılan, bağlayıcı için modül girişi olarak .obj dosyaları kullanın ve .lib kitaplık dosyası oluşturur.  
  
-   Modüllerinizi yönetilen kitaplık oluşturmak için kullanılan ve bağlayıcı için tüm modül girişi (/ CLR: safe ile üretilen) doğrulanabilir olacaksa, bağlayıcı için modül girişi olarak .obj dosyaları kullanın ve .dll (derleme) veya .netmodule (modül) kitaplık dosyası oluşturun.  
  
-   Modüllerinizi yönetilen kitaplık oluşturmak için kullanılan ve bağlayıcı için tüm modül girişi ile üretilen **/CLR: pure** veya **/CLR: safe**, bağlayıcı için modül girişi olarak .obj dosyaları kullanın ve .dll (Oluştur derleme) veya .netmodule (yalnızca yönetilen tür kitaplığından kullanıma sunmak istiyorsanız Modülü). **/CLR: pure** ve **/CLR: safe** derleyici seçenekleri Visual Studio 2015'te kullanım dışı. Kitaplığı'ndan yönetilen türler ve ayrıca yerel türler Kitaplığı'nda kullanmak için C++ uygulamaları istiyorsanız kullanıma sunmak istiyorsanız, kitaplık (aynı zamanda her modül için .h dosyaları sevk etmek istediğiniz kitaplıkları bileşen modülleri .obj dosyaları oluşur ile başvurulabilir şekilde # kaynak kodundan include).  
  
-   Modüllerinizi yönetilen kitaplık oluşturmak için kullanılan ve bağlayıcı için bir veya daha fazla modülleri giriş yalnızca/CLR ile üretilecek, bağlayıcı için modül girişi olarak .obj dosyaları kullanın ve .dll (derleme) oluşturur.  Kitaplığı'ndan yönetilen türler ve ayrıca yerel türler Kitaplığı'nda kullanmak için C++ uygulamaları istiyorsanız kullanıma sunmak istiyorsanız, kitaplık (aynı zamanda her modül için .h dosyaları sevk etmek istediğiniz kitaplıkları bileşen modülleri .obj dosyaları oluşur ile başvurulabilir şekilde # kaynak kodundan include).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlayıcı Girişi olarak .netmodule Dosyaları](../../build/reference/netmodule-files-as-linker-input.md)