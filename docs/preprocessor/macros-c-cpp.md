---
title: Makrolar (C/C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- preprocessor
- preprocessor, macros
- Visual C++, preprocessor macros
ms.assetid: a7bfc5d4-2537-4fe0-bef0-70cec0b43388
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6794cb56566e552a47f19d53f4092c1a9749969c
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33850189"
---
# <a name="macros-cc"></a>Makrolar (C/C++)
Ön işleme genişletir önişlemci yönergeleri değil tüm satırlarda makroları (olmayan satırlar bir **#** ilk boşluk olmayan karakter olarak) ve bir parçası olarak atlandı olmayan bazı yönergeleri bölümlerinde bir Koşullu derleme. "Koşullu derleme" yönergeleri, sabit bir ifade test ederek, bir kaynak dosyanın parçalarını derlenmesini gizlemek izin vermek veya hangi metin blokları belirlemek için tanımlayıcı geçirilir derleyici ve hangi metin blokları sırasında kaynak dosyadan kaldırılır ön işleme.  
  
 `#define` Yönergesi genellikle anlamlı tanımlayıcıları sabitleri, anahtar sözcükler ve sık kullanılan deyimler veya ifadeler ile ilişkilendirmek için kullanılır. Sabitler temsil tanımlayıcıları bazen "sembolik sabitler" veya "sabitleri bildirim" adı verilir Deyimleri ya da ifadeleri temsil tanımlayıcıları "makroları." olarak adlandırılır Önişlemci bu belgede, yalnızca "makrosu" terimi kullanılır.  
  
 Makro adını tanınmıyor program kaynak metin veya belirli bir önişlemci komutlar bağımsız değişkenleri, o makrosu çağrısı olarak kabul edilir. Makro adını makrosu gövdesi bir kopyasını tarafından değiştirilir. Makro bağımsız değişkenleri kabul ederse makrosu adından gerçek bağımsız değişkenler makrosu gövdesindeki biçimsel parametresi için yerine kullanılır. Makro çağrı gövdesi işlenen kopyası ile değiştirme işlemi makrosu çağrının "genişletme" adı verilir.  
  
 Pratikteki, iki tür makro vardır. Böylece arayın ve işlev çağrıları gibi davranacak bağımsız değişkenleri kabul etmek için "işlevi benzeri" makroları tanımlanabilir ise "Nesne benzeri" makroları, bağımsız değişkenler almayan. Makroları gerçek işlev çağrılarını oluşturmaz olduğundan, bazen programların işlev çağrılarını makroları ile değiştirerek daha hızlı çalıştırılması yapabilirsiniz. (C++'da, satır içi işlevler genellikle bir tercih edilen yöntemdir.) Ancak, eğer değil tanımlayın ve bunları dikkatli kullanın makroları sorunları oluşturabilir. İfadedeki uygun öncelik korumak için bağımsız değişkenlerle makro tanımlarında parantez kullanmak zorunda kalabilirsiniz. Ayrıca, makroları doğru yan etkileri ifadelerle işleyebilir değil. Bkz: `getrandom` örnekte [#define yönergesi](../preprocessor/hash-define-directive-c-cpp.md) daha fazla bilgi için.  
  
 Makro tanımladıktan sonra orijinal tanımını kaldırmadan farklı bir değer olarak tanımlanamaz. Ancak, tam olarak aynı tanımıyla makrosu tanımlayabilirsiniz. Bu nedenle, aynı tanımın bir program içinde birden fazla kez görünebilir.  
  
 #**Undef** yönergesi bir makro tanımı kaldırır. Tanımı kaldırıldıktan sonra farklı bir değer makrosuna tanımlayabilirsiniz. [#Define yönergesi](../preprocessor/hash-define-directive-c-cpp.md) ve [#undef yönergesi](../preprocessor/hash-undef-directive-c-cpp.md) ele `#define` ve `#undef` yönergeleri, sırasıyla.  
  
 Daha fazla bilgi için bkz:  
  
-   [Makrolar ve C++](../preprocessor/macros-and-cpp.md)  
  
-   [Variadic Makrolar](../preprocessor/variadic-macros.md)  
  
-   [Önceden Tanımlanmış Makrolar](../preprocessor/predefined-macros.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C/C++ Ön İşlemci Başvurusu](../preprocessor/c-cpp-preprocessor-reference.md)