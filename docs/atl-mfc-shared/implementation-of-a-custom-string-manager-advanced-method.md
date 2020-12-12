---
description: 'Daha fazla bilgi edinin: özel bir dize yöneticisinin uygulanması (Gelişmiş Yöntem)'
title: Özel bir dize Yöneticisi (Gelişmiş Yöntem) uygulama
ms.date: 11/04/2016
helpviewer_keywords:
- IAtlStringMgr class, using
ms.assetid: 64ab7da9-47c1-4c4a-9cd7-4cc37e7f3f57
ms.openlocfilehash: 042c0759076d14e2fd0cf8dd91e34c4f1d8bb534
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97166973"
---
# <a name="implementation-of-a-custom-string-manager-advanced-method"></a>Özel bir dize Yöneticisi (Gelişmiş Yöntem) uygulama

Özel durumlarda, yalnızca bellek ayırmak için kullanılan yığını değiştirme özelliğinden daha fazla olan özel bir dize Yöneticisi uygulamak isteyebilirsiniz. Bu durumda, [IAtlStringMgr](../atl-mfc-shared/reference/iatlstringmgr-class.md) arabirimini özel dize yöneticiniz olarak elle uygulamanız gerekir.

Bunu yapmak için ilk olarak, [CStringT](../atl-mfc-shared/reference/cstringt-class.md) 'nin dize verilerini yönetmek için bu arabirimi nasıl kullandığını anlamak önemlidir. Her örneğinin, `CStringT` [CStringData](../atl-mfc-shared/reference/cstringdata-class.md) yapısına yönelik bir işaretçisi vardır. Bu değişken uzunluklu yapı, dize için gerçek karakter verilerinin yanı sıra dize hakkındaki önemli bilgileri (uzunluk gibi) içerir. Her özel dize Yöneticisi, isteği için bu yapıları ayırmayı ve boşaltmayı sağlamaktan sorumludur `CStringT` .

`CStringData`Yapı dört alandan oluşur:

- [pStringMgr](../atl-mfc-shared/reference/cstringdata-class.md#pstringmgr) Bu alan, `IAtlStringMgr` Bu dize verilerini yönetmek için kullanılan arabirimi işaret eder. `CStringT`Dize arabelleğini yeniden tahsis etmeniz veya boşaltması gerektiğinde, bu arabirimin yeniden tahsis veya ücretsiz yöntemleri, `CStringData` yapıyı parametre olarak geçirerek çağırır. `CStringData`String Manager 'da bir yapı ayrılırken, bu alanı özel dize yöneticinize işaret etmek üzere ayarlamanız gerekir.

- [nDataLength](../atl-mfc-shared/reference/cstringdata-class.md#ndatalength) Bu alan, Sonlandırıcı null değeri hariç arabellekte depolanan dizenin geçerli mantıksal uzunluğunu içerir. `CStringT` dizenin uzunluğu değiştiğinde bu alanı güncelleştirir. Bir yapı ayrılırken `CStringData` , dize yöneticinizin bu alanı sıfıra ayarlaması gerekir. Bir `CStringData` yapıyı yeniden konumlandırdığınızda, özel dize yöneticinizin bu alanı değiştirmeden bırakması gerekir.

- [nAllocLength](../atl-mfc-shared/reference/cstringdata-class.md#nalloclength) Bu alan, bu dize arabelleğinde depolanabilecek en fazla karakter sayısını (Sonlandırıcı null hariç) içerir. `CStringT`Dizenin mantıksal uzunluğunu artırması gerektiğinde, arabellekte yeterli alan olduğundan emin olmak için ilk olarak bu alanı denetler. Denetim başarısız olursa, `CStringT` arabelleği yeniden ayırmak için özel dize yöneticinize çağrı yapılır. Bir yapıyı ayırırken veya yeniden konumlandırdığınızda `CStringData` , bu alanı en az *nChars* parametresinde [IAtlStringMgr:: allocate](../atl-mfc-shared/reference/iatlstringmgr-class.md#allocate) veya [IAtlStringMgr:: yeniden ayrılacak](../atl-mfc-shared/reference/iatlstringmgr-class.md#reallocate)şekilde ayarlamanız gerekir. Arabellekte istenenden daha fazla alan varsa, bu değeri kullanılabilir gerçek alan miktarını yansıtacak şekilde ayarlayabilirsiniz. Bu, `CStringT` arabelleği yeniden ayırmak için dize yöneticisine geri çağrı yapmadan önce, ayrılan alanın tamamını dolduracak şekilde dizeyi büyütmeye olanak tanır.

- [nRefs](../atl-mfc-shared/reference/cstringdata-class.md#nrefs) Bu alan, dize arabelleğinin geçerli başvuru sayısını içerir. Değer bir ise, tek bir örneği `CStringT` arabelleği kullanmaktır. Ayrıca, örneğin, arabelleğin içeriğini okumasına ve değiştirmesine izin verilir. Değer birden büyükse, birden çok örneği `CStringT` arabelleği kullanabilir. Karakter arabelleği paylaşıldığından, `CStringT` örnekler yalnızca arabelleğin içeriğini okuyabilir. İçeriği değiştirmek için `CStringT` önce arabelleğin bir kopyasını oluşturur. Değer negatifse, yalnızca bir örneği `CStringT` arabelleği kullanmaktır. Bu durumda, arabellek kilitli kabul edilir. Bir `CStringT` örnek kilitli bir arabellek kullanırken başka bir örneği `CStringT` , arabelleği paylaşabilir. Bunun yerine, bu örnekler içerikleri değiştirmeden önce arabelleğin bir kopyasını oluşturur. Ayrıca, `CStringT` kilitli arabelleği kullanan örnek, kendisine atanmış başka bir örneğin arabelleğini paylaşmaya çalışmaz `CStringT` . Bu durumda, `CStringT` örnek diğer dizeyi kilitli arabelleğe kopyalar.

   Bir yapı ayrılırken `CStringData` , bu alanı arabellek için izin verilen paylaşım türünü yansıtacak şekilde ayarlamanız gerekir. Çoğu uygulama için bu değeri bir olarak ayarlayın. Bu, normal kopyalama yazma paylaşım davranışına izin verir. Ancak, dize yöneticiniz dize arabelleğini paylaşmayı desteklemiyorsa, bu alanı kilitli bir duruma ayarlayın. Bu `CStringT` , yalnızca bu arabelleği ayrılan örneği için kullanmayı zorlar `CStringT` .

## <a name="see-also"></a>Ayrıca bkz.

[CStringT ile bellek yönetimi](../atl-mfc-shared/memory-management-with-cstringt.md)
