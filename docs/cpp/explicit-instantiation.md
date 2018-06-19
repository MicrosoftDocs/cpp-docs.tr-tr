---
title: Açık örnekleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- templates, instantiation
- explicit instantiation
- instantiation, explicit
ms.assetid: 8b0d4e32-45a6-49d5-8041-1ebdd674410e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f4925a60843ada350a2795709d9257ab796616a7
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32415193"
---
# <a name="explicit-instantiation"></a>Açık Örnekleme
Gerçekte kodunuzda kullanmadan bir şablonlu sınıfın veya işlevin örneklemesini oluşturmak için açık örneklemeyi kullanabilirsiniz. Bu, dağıtım için şablonlar kullanın kitaplık (.lib) dosyaları oluştururken yararlı olduğundan, örneklenmemiş şablon tanımları nesne (.obj) dosyalarına konmaz.  
  
 Bu kod `MyStack` değişkenleri ve altı öğe için açıkça `int` örneğini oluşturur:  
  
```cpp  
template class MyStack<int, 6>;  
```  
  
 Bu deyim, bir nesne için herhangi bir depolama alanı ayırmadan bir `MyStack` örneklemesi oluşturur. Tüm üyeler için kod oluşturulur.  
  
 Bir sonraki satır yalnızca oluşturucu üye işlevinin örneğini açıkça oluşturur:  
  
```cpp  
template MyStack<int, 6>::MyStack( void );  
```  
  
 Belirli tür bağımsız değişkeni bunları yeniden bildirmek için örnekte gösterildiği gibi kullanarak açıkça işlev şablonları bir örneğini oluşturabilirsiniz [işlev şablonu örneklemesi](../cpp/function-template-instantiation.md).  
  
 Üyelerin örneklemelerinin otomatik olarak oluşturulmasını önlemek için `extern` anahtar sözcüğünü kullanabilirsiniz. Örneğin:  
  
```cpp  
extern template class MyStack<int, 6>;  
```  
  
 Benzer şekilde, belirli üyeleri dış ve örneklenmemiş olarak işaretleyebilirsiniz:  
  
```cpp  
extern template MyStack<int, 6>::MyStack( void );  
```  
  
 Derleyicinin birden fazla nesne modülünde aynı örnekleme kodunu oluşturmasını önlemek için `extern` anahtar sözcüğünü kullanabilirsiniz. İşlev çağrılırsa, belirtilen açık şablon parametrelerini en az bir bağlantılı modülde kullanarak şablon işlevinin örneğini oluşturmalısınız, aksi takdirde program oluşturulduğunda bir bağlayıcı hatası alırsınız.  
  
> [!NOTE]
>  Uzmanlıktaki `extern` anahtar sözcüğü yalnızca sınıf gövdesinin dışında tanımlanmış üye işlevleri için geçerlidir. Sınıf bildirimi içinde tanımlanmış işlevler, satır içi işlevleri olarak kabul edilir ve her zaman örneği oluşturulur.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İşlev Şablonları](../cpp/function-templates.md)