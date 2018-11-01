---
title: 'CFixedStringT: Örnek özel dize Yöneticisi'
ms.date: 11/04/2016
helpviewer_keywords:
- CFixedStringT class, using a custom string manager
ms.assetid: 1cf11fd7-51b8-4b94-87af-02bc25f47dd6
ms.openlocfilehash: d35c4c998a6e5913cd972312c511b2a102480c81
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50663170"
---
# <a name="cfixedstringt-example-of-a-custom-string-manager"></a>CFixedStringT: Örnek özel dize Yöneticisi

ATL kitaplığı uygulayan bir sınıf tarafından kullanılan bir özel dize Yöneticisi örneği [CFixedStringT](../atl-mfc-shared/reference/cfixedstringt-class.md)adlı **CFixedStringMgr**. `CFixedStringT` türetilen [CStringT](../atl-mfc-shared/reference/cstringt-class.md) ve karakter verilerini ayıran bir parçası olarak bir dize uygulayan `CFixedStringT` dizesi tarafından belirtilen uzunluğundan az olduğu sürece kendisini nesne `t_nChars` şablonparametresi`CFixedStringT`. Bu yaklaşımda, sabit arabellek boyutu dize uzunluğu arttıkça sürece dize yığın hiç gerekmez. Çünkü `CFixedStringT` mu her zaman kullanın, dize verileri, ayırmak için bir yığın kullanamazsınız `CAtlStringMgr` kendi dize Yöneticisi olarak. Bir özel dize Yöneticisi'ni kullanır (`CFixedStringMgr`), uygulama [Iatlstringmgr](../atl-mfc-shared/reference/iatlstringmgr-class.md) arabirimi. Bu arabirim içinde ele alınmıştır [uygulama özel dize Yöneticisi (Gelişmiş yöntem)](../atl-mfc-shared/implementation-of-a-custom-string-manager-advanced-method.md).

Oluşturucusu `CFixedStringMgr` üç parametreleri alır:

- *pData:* sabit bir işaretçi `CStringData` kullanılacak yapısı.

- *nChars:* maksimum karakter sayısını `CStringData` yapısı tutabilir.

- *pMgr:* işaretçisi `IAtlStringMgr` arabirimi manager'ın bir"Yedekleme dize."

Oluşturucu değerlerini depolar *pData* ve *pMgr* , ilgili üye değişkenlerine (`m_pData` ve `m_pMgr`). Ardından, sıfır olarak sabit arabellek başvuru sayısı-1 ve en büyük boyutuna eşit kullanılabilir uzunluğu arabellek uzunluğunu ayarlar. Başvuru sayısı değeri arabellek kilitli gösterir ve bu örneği kullanmak için `CFixedStringMgr` dize Yöneticisi olarak.

Arabellek kilitli olarak işaretlemek, engeller diğer `CStringT` arabellek paylaşılan bir başvuru tutan gelen örnekleri. Başka `CStringT` örnekleri izin verilen olacağını tarafından içerilen arabellek için olası arabellek paylaşmak için `CFixedStringT` diğer dizeleri hala arabellek kullandığınız sırada silinecek.

`CFixedStringMgr` tam bir uygulamasıdır `IAtlStringMgr` arabirimi. Her yöntemin uygulanmasını ayrı olarak ele alınmıştır.

## <a name="implementation-of-cfixedstringmgrallocate"></a>CFixedStringMgr::Allocate uygulaması

Uygulamasını `CFixedStringMgr::Allocate` dize istenen boyutu sabit arabellek boyutu küçük veya ona eşit olup olmadığını denetler (depolanan `m_pData` üyesi). Sabit arabellek yeteri kadar büyük olursa `CFixedStringMgr` sabit arabellek uzunluğu sıfır kilitler. Dize uzunluğu dışında sabit arabellek boyutunu büyütün değil sürece `CStringT` arabellek yeniden tahsis olmaz.

Dize istenen boyutu sabit arabellekten daha büyük olup olmadığı `CFixedStringMgr` için yedekleme dize Yöneticisi isteği iletir. Öbek arabelleğinden ayırmak için yedekleme dize Yöneticisi'ni kabul edilir. Ancak bu arabellek dönmeden önce `CFixedStringMgr` arabellek kilitler ve arabellek dize manager işaretçi işaretçisi ile değiştirir `CFixedStringMgr` nesne. Bu denemelerinin yeniden tahsis ya da boş arabellek sağlar `CStringT` içine çağıracak `CFixedStringMgr`.

## <a name="implementation-of-cfixedstringmgrreallocate"></a>CFixedStringMgr::ReAllocate uygulaması

Uygulamasını `CFixedStringMgr::ReAllocate` için uygulaması çok benzer `Allocate`.

Sabit arabellek önceliksiz arabellek ise ve istenen arabellek boyutu sabit arabellek küçüktür, hiçbir ayırma gerçekleştirilir. Ancak, önceliksiz arabellek sabit arabellek değilse yedekleme Yöneticisi ile ayrılan bir arabellek olması gerekir. Bu durumda yedekleme Yöneticisi arabellek yeniden ayırmak üzere kullanılır.

Önceliksiz arabellek sabit arabellek ve yeni arabellek boyutu sabit arabellek içinde sığmayacak kadar büyük ise `CFixedStringMgr` yedekleme Yöneticisi'ni kullanarak yeni bir arabelleği ayırır. Sabit arabellek içeriği daha sonra yeni belleğe kopyalanır.

## <a name="implementation-of-cfixedstringmgrfree"></a>CFixedStringMgr::Free uygulaması

Uygulamasını `CFixedStringMgr::Free` olarak aynı deseni izler `Allocate` ve `ReAllocate`. Bırakılan arabellek sabit arabellek ise, yöntem bir sıfır uzunluklu kilitli arabellek ayarlar. Bırakılan arabellek yedek yöneticisiyle ayırdığınızda `CFixedStringMgr` ücretsiz için yedekleme Yöneticisi'ni kullanır.

## <a name="implementation-of-cfixedstringmgrclone"></a>CFixedStringMgr::Clone uygulaması

Uygulamasını `CFixedStringMgr::Clone` her zaman yedek Yöneticisi için bir işaretçi döndürür yerine `CFixedStringMgr` kendisi. Çünkü böyle her örneğini `CFixedStringMgr` yalnızca tek bir örneği ile ilişkili olabilir `CStringT`. Diğer örneklerini `CStringT` manager kopyalamayı deneyen almanız gerekir yedekleme Yöneticisi yerine. Yedekleme Yöneticisi paylaşılmasını destekleyen olmasıdır.

## <a name="implementation-of-cfixedstringmgrgetnilstring"></a>CFixedStringMgr::GetNilString uygulaması

Uygulamasını `CFixedStringMgr::GetNilString` sabit arabelleğini döndürür. Bire iletişimi nedeniyle `CFixedStringMgr` ve `CStringT`, belirli bir örneğini `CStringT` hiçbir zaman aynı anda birden fazla arabellek kullanır. Bu nedenle, boş bir dize ve bir gerçek bir dize arabelleğine hiçbir zaman aynı anda gereklidir.

Sabit Arabellek kullanımda değil her `CFixedStringMgr` sıfır uzunlukta başlatılır sağlar. Bu boş dize olarak kullanılmasını sağlar. Eklenen bir ek olarak `nAllocLength` sabit arabellek üye her zaman sabit arabellek tam boyuta ayarlayın. Diğer bir deyişle `CStringT` çağırmadan dize büyüyebilir [IAtlStringMgr::Reallocate](../atl-mfc-shared/reference/iatlstringmgr-class.md#reallocate)nil dize için bile.

## <a name="requirements"></a>Gereksinimler

**Başlık:** cstringt.h

## <a name="see-also"></a>Ayrıca Bkz.

[CStringT ile Bellek Yönetimi](../atl-mfc-shared/memory-management-with-cstringt.md)

