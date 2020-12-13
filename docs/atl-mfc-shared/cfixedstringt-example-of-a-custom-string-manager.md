---
description: 'Daha fazla bilgi edinin: CFixedStringT: özel bir dize Yöneticisi örneği'
title: 'CFixedStringT: özel bir dize Yöneticisi örneği'
ms.date: 11/04/2016
helpviewer_keywords:
- CFixedStringT class, using a custom string manager
ms.assetid: 1cf11fd7-51b8-4b94-87af-02bc25f47dd6
ms.openlocfilehash: c9af2530500ad5972c01d063116e7ac981109493
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97142512"
---
# <a name="cfixedstringt-example-of-a-custom-string-manager"></a>CFixedStringT: özel bir dize Yöneticisi örneği

ATL Kitaplığı, CFixedStringT adlı sınıf tarafından kullanılan özel bir dize [](../atl-mfc-shared/reference/cfixedstringt-class.md)yöneticisinin bir örneğini **uygular.** `CFixedStringT` , [CStringT](../atl-mfc-shared/reference/cstringt-class.md) 'den türetilir ve `CFixedStringT` dize, şablon parametresi tarafından belirtilen uzunluktan daha az olduğu sürece, kendi karakter verilerini nesnenin bir parçası olarak ayıran bir dize uygular `t_nChars` `CFixedStringT` . Bu yaklaşımla, dizenin uzunluğu sabit arabelleğin ötesine genişlemediği takdirde dize her bir yığına gerektirmez. `CFixedStringT`, Dize verilerini ayırmak için her zaman bir yığın kullanmadığından, `CAtlStringMgr` dize Yöneticisi olarak kullanamaz. Bu `CFixedStringMgr` , [IAtlStringMgr](../atl-mfc-shared/reference/iatlstringmgr-class.md) arabirimini uygulayan özel bir dize Yöneticisi () kullanır. Bu arabirim, [özel bir dize Yöneticisi (Gelişmiş Yöntem) uygulamasında](../atl-mfc-shared/implementation-of-a-custom-string-manager-advanced-method.md)ele alınmıştır.

İçin Oluşturucu `CFixedStringMgr` üç parametre alır:

- *pData:* Kullanılacak sabit yapıya yönelik bir işaretçi `CStringData` .

- *nChars:* Yapının tutabilecek en fazla karakter sayısı `CStringData` .

- *pMgr:* `IAtlStringMgr` "Yedekleme dizesi Yöneticisi" arabirimine yönelik bir işaretçi.

Oluşturucu, *pData* ve *pMgr* değerlerini ilgili üye değişkenlerinde ( `m_pData` ve `m_pMgr` ) depolar. Ardından, arabelleğin uzunluğunu sıfıra, kullanılabilir uzunluğu sabit arabelleğin en büyük boyutuna, ve başvuru sayısını-1 olarak ayarlar. Başvuru sayısı değeri, arabelleğin kilitli olduğunu ve bu örneğini `CFixedStringMgr` dize Yöneticisi olarak kullanacağını gösterir.

Arabelleği kilitli olarak işaretlemek, diğer `CStringT` örneklerin arabelleğe bir paylaşılan başvuru tutmasını önler. Diğer `CStringT` örneklerin arabelleği paylaşmasına izin veriliyorsa, `CFixedStringT` diğer dizeler halen arabelleği kullanırken, tarafından içerilen arabelleğin silinmesi mümkün olacaktır.

`CFixedStringMgr` , arabirimin tam bir uygulamasıdır `IAtlStringMgr` . Her yöntemin uygulanması ayrı olarak ele alınmıştır.

## <a name="implementation-of-cfixedstringmgrallocate"></a>CFixedStringMgr:: allocate uygulama

İlk olarak, `CFixedStringMgr::Allocate` dizenin istenen boyutunun sabit arabelleğin (üyede depolanan) boyutundan küçük veya ona eşit olup olmadığını denetler `m_pData` . Sabit arabellek yeterince büyükse, `CFixedStringMgr` sabit arabelleği sıfır uzunluğuna kilitler. Dize uzunluğu sabit arabelleğin boyutunun ötesinde büyümediğinde, `CStringT` arabelleği yeniden ayırmak zorunda değildir.

Dizenin istenen boyutu sabit arabellekten büyükse `CFixedStringMgr` , isteği yedekleme dize yöneticisine iletir. Yedekleme dize Yöneticisi, yığındaki arabelleği ayırmak için kullanılır. Ancak, bu arabelleği döndürmeden önce `CFixedStringMgr` arabelleği kilitler ve arabelleğin dize Yöneticisi işaretçisini nesnenin işaretçiyle değiştirir `CFixedStringMgr` . Bu, arabelleği yeniden ayırma veya serbest bırakma girişimlerinin ' i `CStringT` çağırabilmesini sağlar `CFixedStringMgr` .

## <a name="implementation-of-cfixedstringmgrreallocate"></a>CFixedStringMgr:: yeniden tahsis uygulama

Uygulamasının uygulamasına uygulanması `CFixedStringMgr::ReAllocate` çok benzerdir `Allocate` .

Yeniden ayrılan arabellek sabit arabellekte ise ve istenen arabellek boyutu sabit arabellekten küçükse, hiçbir ayırma yapılmaz. Ancak, yeniden ayrılan arabellek sabit arabellek değilse, Yedekleme Yöneticisi ile ayrılmış bir arabellek olması gerekir. Bu durumda, arabelleği yeniden ayırmak için Yedekleme Yöneticisi kullanılır.

Yeniden ayrılan arabellek sabit arabellekte ise ve yeni arabellek boyutu sabit arabelleğe sığmayacak kadar büyükse, `CFixedStringMgr` Backup Manager 'ı kullanarak yeni bir arabellek ayırır. Sabit arabelleğin içeriği daha sonra yeni arabelleğe kopyalanır.

## <a name="implementation-of-cfixedstringmgrfree"></a>CFixedStringMgr:: Free uygulama

Uygulamasının uygulanması, `CFixedStringMgr::Free` ve ile aynı kalıbı izler `Allocate` `ReAllocate` . Serbest bırakılmakta olan arabellek sabit arabellekte ise, yöntemi sıfır uzunluklu bir kilitli arabelleğe ayarlar. Serbest bırakılmakta olan arabellek Yedekleme Yöneticisi ile ayrıldıysa, `CFixedStringMgr` bunu serbest bırakmak için yedekleme yöneticisini kullanır.

## <a name="implementation-of-cfixedstringmgrclone"></a>CFixedStringMgr:: Clone uygulama

Uygulamasının uygulanması, `CFixedStringMgr::Clone` her zaman Yedekleme Yöneticisi yerine bir işaretçi döndürür `CFixedStringMgr` . Bu durum, her örneği `CFixedStringMgr` yalnızca öğesinin tek bir örneğiyle ilişkilendirilemediğinden oluşur `CStringT` . `CStringT`Yöneticiyi kopyalamaya çalışan diğer tüm örnekler bunun yerine yedekleme yöneticisini almalıdır. Bunun nedeni, yedekleme yöneticisinin paylaşılmakta olmasını desteklemedir.

## <a name="implementation-of-cfixedstringmgrgetnilstring"></a>CFixedStringMgr:: GetNilString uygulamasının uygulanması

Uygulamasının uygulanması, `CFixedStringMgr::GetNilString` sabit arabelleği döndürür. Ve ' nin bire bir yazışmaları nedeniyle `CFixedStringMgr` `CStringT` , belirli bir örneği `CStringT` hiçbir zaman aynı anda birden fazla arabellek kullanmaz. Bu nedenle, bir Nil dize ve gerçek bir dize arabelleği aynı anda hiçbir zaman gerekli değildir.

Sabit arabellek kullanımda olmadığı zaman, `CFixedStringMgr` sıfır uzunlukla başlatılmış olmasını sağlar. Bu, Nil dize olarak kullanılmasına izin verir. Ek olarak, `nAllocLength` sabit arabelleğin üyesi her zaman sabit arabelleğin tam boyutuna ayarlanır. Bu, `CStringT` Nil dize için bile [IAtlStringMgr::](../atl-mfc-shared/reference/iatlstringmgr-class.md#reallocate)yeniden ayırma çağrılmadan dizeyi büyüyebileceği anlamına gelir.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** CStringT. h

## <a name="see-also"></a>Ayrıca bkz.

[CStringT ile bellek yönetimi](../atl-mfc-shared/memory-management-with-cstringt.md)
