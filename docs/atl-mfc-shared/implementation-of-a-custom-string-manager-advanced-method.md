---
title: Uygulama özel dize Yöneticisi (Gelişmiş yöntem)
ms.date: 11/04/2016
helpviewer_keywords:
- IAtlStringMgr class, using
ms.assetid: 64ab7da9-47c1-4c4a-9cd7-4cc37e7f3f57
ms.openlocfilehash: 3854ffe205aa8e6cb9cfb800b9aa1473094fffaf
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62235505"
---
# <a name="implementation-of-a-custom-string-manager-advanced-method"></a>Uygulama özel dize Yöneticisi (Gelişmiş yöntem)

Özel durumlarda, daha fazlasını hangi yığın bellek ayırmak için kullanılan değişmez bir özel dize Yöneticisi uygulamak isteyebilirsiniz. Bu durumda, el ile uygulamalısınız [Iatlstringmgr](../atl-mfc-shared/reference/iatlstringmgr-class.md) arabirimi, özel dize Yöneticisi olarak.

Bunu yapmak için öncelikle anlamanız önemlidir nasıl [CStringT](../atl-mfc-shared/reference/cstringt-class.md) dize verilerini yönetmek için bu arabirimi kullanır. Her bir örneğini `CStringT` bir işaretçiye sahip bir [CStringData](../atl-mfc-shared/reference/cstringdata-class.md) yapısı. Bu değişken uzunluklu yapı gerçek karakter veri dizesi için yanı sıra dize (örneğin, uzunluk) hakkında önemli bilgiler içerir. Her özel dize Yöneticisi tahsis etme ve bu isteği yapıları serbest bırakma sorumludur `CStringT`.

`CStringData` Yapısını oluşturan dört alan:

- [pStringMgr](../atl-mfc-shared/reference/cstringdata-class.md#pstringmgr) Bu alan işaret `IAtlStringMgr` Bu dize verileri yönetmek için kullanılan arabirim. Zaman `CStringT` yeniden tahsis ya da yeniden ayırma veya geçirerek bu arabirim, ücretsiz yöntemlerinin çağırdığı dize arabelleğindeki ücretsiz gereken `CStringData` yapısı bir parametre olarak. Ayırma sırasında bir `CStringData` yapısı, dize Yöneticisi'nde, bu alan için özel dize Yöneticisi işaret edecek şekilde ayarlamanız gerekir.

- [nDataLength](../atl-mfc-shared/reference/cstringdata-class.md#ndatalength) Bu alan geçerli mantıksal bir sonlandırıcı null dışında arabellekteki depolanan dize uzunluğu içerir. `CStringT` dize uzunluğu değiştiğinde bu alanı günceller. Ayırma sırasında bir `CStringData` yapısı, dize Yöneticisi'ni ayarlamanız gerekir bu alan için sıfır. Ayrılırken bir `CStringData` yapısı, özel dize Yöneticisi'ni gerekir bırakın değiştirmeden Bu alan.

- [nAllocLength](../atl-mfc-shared/reference/cstringdata-class.md#nalloclength) tahsis olmadan bu dize arabellek depolanabilir (Sonlandırıcı null dışında) karakter sayısı bu alan içerir. Her `CStringT` mantıksal dize uzunluğunu artırmak gereken ilk arabellekteki yeterli boş alan olduğundan emin olmak için bu alanı denetler. Denetimi başarısız olursa `CStringT` arabellek yeniden ayırmak üzere özel dize Yöneticisi'ni çağırıyor. Ayırma ya da yeniden ayırma bir `CStringData` yapısını ayarlamanız gerekir bu en az içinde istenen karakter sayısı alanı *nChars* parametresi [IAtlStringMgr::Allocate](../atl-mfc-shared/reference/iatlstringmgr-class.md#allocate) veya [IAtlStringMgr::Reallocate](../atl-mfc-shared/reference/iatlstringmgr-class.md#reallocate). Arabellek istenenden daha fazla alan varsa, bu değer, gerçek kullanılabilir alan miktarını yansıtacak şekilde ayarlayabilirsiniz. Böylece `CStringT` arabellek ayrılacak dize Yöneticisi'ne geri çağırmaya sahip önce dizenin tamamını dolduracak şekilde ulaşması için ayrılan alan.

- [nRefs](../atl-mfc-shared/reference/cstringdata-class.md#nrefs) Bu alan dize arabelleğinin geçerli başvuru sayısını içerir. Değer bir sonra tek bir örneği ise `CStringT` arabellek kullanıyor. Ayrıca, örneğine hem okuma hem de arabellek içeriğini değiştirmek için izin verilir. Değer bir birimden büyük olursa birden çok örneğini `CStringT` arabellek kullanabilirsiniz. Karakter arabelleği paylaşıldığından, `CStringT` örnekleri arabellek içeriği yalnızca okuyabilir. İçeriğini değiştirmek için `CStringT` ilk arabellek kopyasını oluşturur. Değer ise negatif, yalnızca bir örneğini `CStringT` arabellek kullanıyor. Bu durumda, arabellek olarak kabul edilir kilitli. Olduğunda bir `CStringT` örneği hiçbir diğer örnekleri kilitli bir arabellek kullanarak `CStringT` arabellek paylaşabiliriz. Bunun yerine, bu örnekler, içeriğini değiştirmeden önce bir arabellek kopyasını oluşturun. Ayrıca, `CStringT` diğer arabellek paylaşmak kilitli arabellek kullanarak örneği denemez `CStringT` atanmış örneği. Bu durumda, `CStringT` örnek bir dize kilitli arabelleğe kopyalar.

   Ayırma sırasında bir `CStringData` yapısı, bu alan için arabellek izin paylaşım türü yansıtacak şekilde ayarlamanız gerekir. Çoğu uygulamaları için bu değer birine ayarlayın. Bu genel yazarken kopyalama paylaşım davranış sağlar. Ancak, dize Yöneticisi'ni dize arabelleğindeki paylaşımı desteklemiyorsa bu alan kilitli bir durumda ayarlayın. Bu zorlar `CStringT` örneği için yalnızca bu arabellek kullanılacak `CStringT` , ayrılmış.

## <a name="see-also"></a>Ayrıca bkz.

[CStringT ile Bellek Yönetimi](../atl-mfc-shared/memory-management-with-cstringt.md)
