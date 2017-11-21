---
title: "Düzenlenmiş adlar | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- decorated names, definition
- name decoration [C++]
- names [C++], decorated
ms.assetid: a4e9ae8e-b239-4454-b401-4102793cb344
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 1db1d851e72bcce893f5e49b83b95ebf3366f15a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="decorated-names"></a>Düzenlenmiş Adlar
İşlevler, veri ve nesneleri C ve C++ programlarında dahili olarak düzenlenmiş adlarıyla temsil edilir. A *adı donatılmış* derleyici tarafından oluşturulan bir nesne, veri veya işlev tanımı derleme sırasında kodlanmış bir dize. Çağırma kuralları, türleri, işlev parametrelerini ve diğer bilgi adı ile birlikte kaydeder. Olarak da bilinen bu ad düzenlemesi *ad bozma*nesnelerde yürütülebilir bir dosya bağlarken ve doğru işlevlerin bulunacağı bağlayıcı yardımcı olur.  
  
 Düzenlenmiş adlandırma kuralları çeşitli Visual C++ sürümünde değiştirilmiştir ve ayrıca farklı bir hedef mimarileri üzerinde farklı olabilir. Visual C++, C ve C++ DLL'ler ve kitaplıklar kullanılarak oluşturulan kaynak dosyalarla doğru bağlamak için aynı derleyici araç setini, bayrakları ve hedef mimari kullanarak derlenmesi gerekir.  
  
 **İçeriği**  
  
-   [Düzenlenmiş adlar](#Using)  
  
-   [C++ biçiminin adı donatılmış](#Format)  
  
-   [Bir C biçiminin adı donatılmış](#FormatC)  
  
-   [Adları donatılmış görüntüleme](#Viewing)  
  
-   [Adları ve görüntüleme](#Undecorated)  
  
##  <a name="Using"></a>Düzenlenmiş adlar  
 Normalde, derler kod yazmaya düzenlenmiş adı ve bağlantı başarıyla bilmek zorunda değilsiniz. Düzenlenmiş adlar iç derleyici ve bağlayıcı için bir uygulama ayrıntılarını ' dir. Araçlar ve biçimde adı genellikle işleyebilir. Bağlayıcı ve diğer araçları işlev adı belirttiğinizde, ancak düzenlenmiş adı bazen gereklidir. Örneğin, aşırı yüklenmiş C++ işlevlerini, ad alanları, sınıf Oluşturucular, yok ediciler ve özel üye işlevleri üyeleri eşleşecek şekilde düzenlenmiş adı belirtmeniz gerekir. Seçeneği hakkında ayrıntılı bilgi için bayrakları ve gerekli diğer durumlarda adlar, Araçlar ve kullanmakta olduğunuz seçenekler için belgelere bakın.  
  
 İşlev adı, sınıf, çağırma, dönüş türü veya herhangi bir parametre değiştirirseniz, düzenlenmiş adı da değişir. Bu durumda, yeni düzenlenmiş adı almak ve her yerde düzenlenmiş adı belirtilen kullanmanız gerekir.  
  
 Ad düzenlemesi, ayrıca diğer programlama dilleri veya diğer derleyiciler kullanılarak yazılan kod bağlarken önemlidir. Farklı derleyicileri farklı adı decoration kurallarını kullanın. Yürütülebilir dosyanın başka bir dilde kod bağlar, dışarı aktarılan ve içeri aktarılan adları ve çağırma kuralları eşleştirmek için özel dikkatli olunması gerekir. Assembly dili kod Visual C++ kullanılarak yazılmış kaynak koduna bağlamak için Visual C++ donatılmış adları ve çağırma kuralları kullanmanız gerekir.  
  
##  <a name="Format"></a>C++ biçiminin adı donatılmış  
 Düzenlenmiş adı C++ işlevi için aşağıdaki bilgileri içerir:  
  
-   İşlev adı.  
  
-   Üye işlevi ise işlevi bir üyesi olduğunu sınıfı. Bu işlevini içeren sınıf kapsayan bir sınıf içerir ve benzeri.  
  
-   Bir ad alanının parçası ise işlevi için ait olduğu ad alanını.  
  
-   İşlev parametreleri türleri.  
  
-   Çağırma kuralı.  
  
-   İşlevinin dönüş türü.  
  
 İşlev ve sınıf adları düzenlenmiş adı kodlanır. Düzenlenmiş adı geri kalanı, iç anlamlıdır yalnızca derleyici ve bağlayıcı için bir koddur. Ve ve düzenlenmiş C++ adları örnekleri verilmiştir.  
  
|Ve adı|Düzenlenmiş adı|  
|----------------------|--------------------|  
|`int a(char){int i=3;return i;};`|`?a@@YAHD@Z`|  
|`void __stdcall b::c(float){};`|`?c@b@@AAGXM@Z`|  
  
##  <a name="FormatC"></a>Bir C biçiminin adı donatılmış  
 C işlevi için decoration form bildiriminden içinde kullanılan arama kuralı aşağıdaki tabloda gösterildiği gibi bağlıdır. Bu da C++ kodu için bildirilmişse, kullanılan decoration biçimidir `extern "C"` bağlantı. Çağırma kuralı varsayılan `__cdecl`. Bir 64-bit ortamında işlevleri değil donatılmış unutmayın.  
  
|Çağırma kuralı|Düzenleme|  
|------------------------|----------------|  
|`__cdecl`|Alt çizgi baştaki (**_**)|  
|`__stdcall`|Alt çizgi baştaki (**_**) ve sondaki adres işareti (@) ondalık parametre listesinde bayt sayısı ve ardından|  
|`__fastcall`|Baştaki ve sondaki işareti (@) parametre listesinde bayt sayısını temsil eden ondalık bir sayı ve ardından|  
|`__vectorcall`|İki parametre listesinde bayt ondalık bir sayı arkasından işaretlerini (@@) sondaki|  
  
##  <a name="Viewing"></a>Adları donatılmış görüntüleme  
 Verileri, nesne veya işlev tanımı veya prototip içeren kaynak dosyası derledikten sonra sembol adını düzenlenmiş biçiminde elde edebilirsiniz. Düzenlenmiş adlar programınızdaki incelemek için aşağıdaki yöntemlerden birini kullanabilirsiniz:  
  
-   #### <a name="to-use-a-listing-to-view-decorated-names"></a>Düzenlenmiş adlar listesini görüntülemek için kullanma  
  
    1.  Verileri, nesne veya işlev tanımı veya prototip ile içeren kaynak dosyası derleme tarafından listesini oluşturmak [listeleme dosya türü](../../build/reference/fa-fa-listing-file.md) kaynak kodu derleme ayarlama derleyici seçeneği (**/FAs**).  
  
         Örneğin `cl /c /FAs example.cpp` listeleme dosyası oluşturmak için geliştirici komut isteminde example.asm.  
  
    2.  Sonuçta ortaya çıkan listeleme dosyasında PUBLIC ile başlar ve ardından ve veri veya işlev adı noktalı virgül biten satırını bulun. Genel ve noktalı virgül arasında simge düzenlenmiş addır.  
  
-   #### <a name="to-use-dumpbin-to-view-decorated-names"></a>Düzenlenmiş adlar DUMPBIN görüntülemek için kullanma  
  
    1.  Dışarı aktarılan simgeleri .obj veya .lib dosyasındaki görmek için girin `dumpbin /symbols` `objfile` bir geliştirici komut isteminde.  
  
    2.  Bir simge düzenlenmiş biçiminde bulmak için parantez içinde ve adını arayın. Düzenlenmiş adı olduğu aynı satırda bir kanal (&#124;) sonra karakter ve ve adından önce.  
  
##  <a name="Undecorated"></a>Adları ve görüntüleme  
 Düzenlenmiş adı ve biçimine dönüştürmek için undname.exe kullanabilirsiniz. Bu örnekte, nasıl çalıştığı gösterilmektedir:  
  
```  
C:\>undname ?func1@a@@AAEXH@Z  
Microsoft (R) C++ Name Undecorator  
Copyright (C) Microsoft Corporation. All rights reserved.  
  
Undecoration of :- "?func1@a@@AAEXH@Z"  
is :- "private: void __thiscall a::func1(int)"  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C/C++ derleme araçları](../../build/reference/c-cpp-build-tools.md)   
 [Bağlantıyı belirtmek için extern kullanma](../../cpp/using-extern-to-specify-linkage.md)