---
title: "Uygulama bir özel dize (Gelişmiş yöntemi) Yöneticisi'nin | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IAtlStringMgr class, using
ms.assetid: 64ab7da9-47c1-4c4a-9cd7-4cc37e7f3f57
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7e76edc65e5f30fee90f346d5434ecbee320a37a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="implementation-of-a-custom-string-manager-advanced-method"></a>Uygulama bir özel dize Yöneticisi'nin (Gelişmiş yöntemi)
Özel durumlarda hangi yığın bellek ayırmak için kullanılan daha fazlasını değişmez özel bir dize Yöneticisi uygulamak isteyebilirsiniz. Bu durumda, el ile uygulamalıdır [IAtlStringMgr](../atl-mfc-shared/reference/iatlstringmgr-class.md) arabirimi, özel bir dize Yöneticisi olarak.  
  
 Bunu yapmak için önce anlamak önemlidir nasıl [CStringT](../atl-mfc-shared/reference/cstringt-class.md) dize verilerini yönetmek için bu arabirimi kullanır. Her örneğinin `CStringT` gösteren bir işaretçi sahip bir [CStringData](../atl-mfc-shared/reference/cstringdata-class.md) yapısı. Bu değişken uzunlukta yapı dize için gerçek karakter verileri yanı sıra (uzunluk gibi), dize hakkında önemli bilgiler içerir. Her özel bir dize Yöneticisi ayırma ve bu isteği yapıları serbest bırakma sorumludur `CStringT`.  
  
 `CStringData` Yapısı dört alanlarını kapsar:  
  
-   [pStringMgr](../atl-mfc-shared/reference/cstringdata-class.md#pstringmgr) Bu alan işaret `IAtlStringMgr` Bu dize verilerini yönetmek için kullanılan arabirim. Zaman `CStringT` yeniden tahsis edin ya da yeniden ayırma veya geçirme, bu arabirimin ücretsiz yöntemlerini çağırır dize arabelleği serbest gereken `CStringData` bir parametre olarak yapısı. Ayırırken bir `CStringData` yapısı, dize Yöneticisi'nde, bu alan özel bir dize yöneticinize işaret edecek şekilde ayarlamanız gerekir.  
  
-   [nDataLength](../atl-mfc-shared/reference/cstringdata-class.md#ndatalength) Bu alan sonlandırma null hariç arabellekte depolanan dizesi geçerli mantıksal uzunluğu içerir. `CStringT`dize uzunluğu değiştiğinde bu alanı güncelleştirir. Ayırırken bir `CStringData` yapısı, dize yöneticinize ayarlamanız gerekir bu alan için sıfır. Ayrılırken bir `CStringData` yapısı, özel bir dize yöneticinize gerekir bırakın değişmeden Bu alan.  
  
-   [nAllocLength](../atl-mfc-shared/reference/cstringdata-class.md#nalloclength) Bu alan en fazla Bu dize arabellek yeniden ayırma olmadan depolanabilir (sonlandırma null dışında) karakter sayısını içerir. Her `CStringT` dizesi mantıksal uzunluğu artırmak gereken ilk arabellekte yeterli alan olduğundan emin olmak için bu alanı denetler. Denetimi başarısız olursa `CStringT` arabellek yeniden ayırmak üzere özel bir dize yöneticinize çağrılar. Ayırma ya da yeniden ayırma bir `CStringData` yapısı, ayarlamalısınız bu en az içinde istenen karakter sayısı alanı **nChars** parametresi [IAtlStringMgr::Allocate](../atl-mfc-shared/reference/iatlstringmgr-class.md#allocate) veya [IAtlStringMgr::Reallocate](../atl-mfc-shared/reference/iatlstringmgr-class.md#reallocate). Arabellek istenenden daha fazla alan varsa, bu değer gerçek kullanılabilir alan miktarını yansıtacak şekilde ayarlayabilirsiniz. Böylece `CStringT` arabellek yeniden ayırmak üzere dize Manager'a geri çağırmaya sahip önce dize tamamını dolduracak şekilde ulaşması için ayrılmış alanı.  
  
-   [nRefs](../atl-mfc-shared/reference/cstringdata-class.md#nrefs) dizesi arabelleği geçerli başvuru sayısı bu alan içerir. Değer bir sonra tek bir örneği ise `CStringT` arabellek kullanıyor. Ayrıca, örnek hem okuma hem de arabellek içeriğini değiştirmeye izin verilmez. Değer bir büyükse, birden çok örneğini `CStringT` arabellek kullanabilirsiniz. Karakter arabellek paylaşıldığından, `CStringT` örnekleri yalnızca arabellek içeriğini okuyun. İçeriği değiştirmek için `CStringT` ilk arabellek bir kopyasını oluşturur. Değer negatif, yalnızca bir örneği `CStringT` arabellek kullanıyor. Bu durumda, arabellek kabul kilitli. Zaman bir `CStringT` örneğini diğer hiçbir örneği kilitli bir arabellek kullanarak `CStringT` arabellek paylaşabilir. Bunun yerine, bu örnekler, içeriği değiştirmeden önce arabellek bir kopyasını oluşturun. Ayrıca, `CStringT` diğer arabelleğin paylaşmak kilitli arabellek kullanarak örneğini denemez `CStringT` atanmış örneği. Bu durumda, `CStringT` örneği kilitli arabelleğe diğer dize kopyalar.  
  
     Ayırırken bir `CStringData` yapısı, bu alan için arabellek boyutu izin verilen paylaşımı türü yansıtacak şekilde ayarlamanız gerekir. Çoğu uygulamalar için bu değer bir olarak ayarlayın. Bu genel yazarken kopyalama paylaşım davranış sağlar. Ancak, dize yöneticinize dizesi arabelleği paylaşımı desteklemiyorsa, bu alan için kilitli bir durumda ayarlayın. Bu zorlar `CStringT` yalnızca bu arabellek örneği için kullanmak üzere `CStringT` , ayrılmış.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CStringT ile Bellek Yönetimi](../atl-mfc-shared/memory-management-with-cstringt.md)

