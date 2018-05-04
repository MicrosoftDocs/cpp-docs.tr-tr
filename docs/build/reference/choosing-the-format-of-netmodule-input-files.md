---
title: Giriş dosyaları .netmodule biçimlerinin seçme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
ms.assetid: 4653d1bd-300f-4083-86f5-d1a06f44e61c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 62575d3e816bdc10587e7a4c9cebcea735329ec1
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="choosing-the-format-of-netmodule-input-files"></a>.netmodule Giriş Dosyaları Biçimini Seçme
MSIL .obj dosya (ile derlenmiş [/CLR](../../build/reference/clr-common-language-runtime-compilation.md)) .netmodule dosyası olarak da kullanılabilir.  .obj dosyaları meta verileri ve yerel simgeler içermelidir.  .netmodules yalnızca meta verileri içerir.  
  
 MSIL .obj dosya için diğer Visual Studio derleyici/addmodule derleyici seçeneği geçirin (ancak edebilirsiniz .obj dosya elde edilen derlemeyi parçası haline gelir ve derleme sevk unutmayın).  Örneğin, Visual C# ve Visual Basic/addmodule derleyici seçeneği vardır.  
  
> [!NOTE]
>  Çoğu durumda, bağlayıcıya .obj dosya .net modülünde oluşturulan derlemeden geçmesi gerekir.  Bir .dll veya .netmodule MSIL modülü dosyası bağlayıcıya geçirme içinde LNK1107 neden olabilir.  
  
 aracılığıyla başvuru bunların ilişkili .h dosyaları birlikte .obj dosyaları #include, .netmodule dosyasında yalnızca yönetilen türler bir C++ uygulaması tarafından kullanılabilecek ancak modülü içindeki yerel türler kullanmak C++ uygulamaları izin verin.  .Obj dosyasına geçirmeye çalışırsanız #using yerel türler hakkında bilgi; kullanılamaz # .obj dosyanın .h dosyası yerine include.  
  
 Diğer Visual Studio derleyicileri yalnızca yönetilen bir modül türlerinden kullanmasını sağlayabilirsiniz.  
  
 Visual C++ bağlayıcı modülü giriş olarak bir .netmodule veya .obj dosyası kullanmanız gerekip gerekmediğini belirlemek için aşağıdakileri kullanın:  
  
-   Visual C++ dışında bir Visual Studio derleyici ile oluşturuluyorsa, bir .netmodule oluşturabilir ve bağlayıcı giriş olarak .netmodule kullanın.  
  
-   Modüller ve modüller dışında bir kitaplığı oluşturmak için kullanılan varsa üretmek için Visual C++ derleyicisi kullanıyorsanız, bağlayıcı modülü giriş olarak derleyici tarafından üretilen .obj dosyaları kullanın; .netmodule dosya giriş olarak kullanmayın.  
  
-   Modüllerinizi yerel (olmayan bir yönetilen) kitaplığı oluşturmak için kullanılan, bağlayıcı için modül girişi olarak .obj dosyaları kullanın ve .lib kitaplık dosyası oluşturur.  
  
-   Modüllerinizi yönetilen kitaplık oluşturmak için kullanılan ve bağlayıcı için tüm modül girişi (/ CLR: safe ile üretilen) doğrulanabilir olacaksa, bağlayıcı için modül girişi olarak .obj dosyaları kullanın ve .dll (derleme) veya .netmodule (modül) kitaplık dosyası oluşturun.  
  
-   Modüllerinizi yönetilen kitaplık oluşturmak için kullanılan ve bağlayıcı için bir veya daha fazla modülleri giriş yalnızca/CLR ile üretilecek, bağlayıcı için modül girişi olarak .obj dosyaları kullanın ve .dll (derleme) oluşturur.  Kitaplığı'ndan yönetilen türler ve ayrıca yerel türler Kitaplığı'nda kullanmak için C++ uygulamaları istiyorsanız kullanıma sunmak istiyorsanız, kitaplık (aynı zamanda her modül için .h dosyaları sevk etmek istediğiniz kitaplıkları bileşen modülleri .obj dosyaları oluşur ile başvurulabilir şekilde # kaynak kodundan include).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlayıcı Girişi olarak .netmodule Dosyaları](../../build/reference/netmodule-files-as-linker-input.md)