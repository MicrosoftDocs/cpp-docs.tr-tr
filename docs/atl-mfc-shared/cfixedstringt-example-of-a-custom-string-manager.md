---
title: "CFixedStringT: Örnek bir özel dize Yöneticisi'nin | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: C++
helpviewer_keywords: CFixedStringT class, using a custom string manager
ms.assetid: 1cf11fd7-51b8-4b94-87af-02bc25f47dd6
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7164d2313f5610d1d7e56f5449c81ea9e2282981
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cfixedstringt-example-of-a-custom-string-manager"></a>CFixedStringT: Örnek bir özel dize Yöneticisi'nin
ATL kitaplığı uygulayan bir sınıf tarafından kullanılan özel bir dize Yöneticisi örneği [CFixedStringT](../atl-mfc-shared/reference/cfixedstringt-class.md)adlı **CFixedStringMgr**. `CFixedStringT`türetilmiş [CStringT](../atl-mfc-shared/reference/cstringt-class.md) ve karakter verilerini bir parçası olarak ayıran bir dize uygulayan `CFixedStringT` dizesi tarafından belirtilen uzunluğundan daha küçük olduğu sürece kendisini nesne **t_nChars** Şablon parametresi `CFixedStringT`. Bu yaklaşımda, dize uzunluğu sabit arabellek boyutu büyüdükçe sürece dize öbek hiç gerekmez. Çünkü `CFixedStringT` mu her zaman kullanım dize verilerini ayırmak için bir yığın tarafından kullanılamaz **CAtlStringMgr** dize Yöneticisi olarak. Özel bir dize Yöneticisi kullanır (**CFixedStringMgr**), uygulama [IAtlStringMgr](../atl-mfc-shared/reference/iatlstringmgr-class.md) arabirimi. Bu arabirim içinde ele alınmıştır [uygulaması bir özel dize Yöneticisi'nin (Gelişmiş yöntemi)](../atl-mfc-shared/implementation-of-a-custom-string-manager-advanced-method.md).  
  
 Oluşturucusu **CFixedStringMgr** üç parametre alır:  
  
-   **pData:** sabit bir işaretçi `CStringData` kullanılacak yapısı.  
  
-   **nChars:** en fazla karakter sayısını `CStringData` yapısı basılı tutun.  
  
-   **pMgr:** gösteren bir işaretçi `IAtlStringMgr` arabirimi "Yedekleme dize yöneticinin."  
  
 Oluşturucusu değerlerini depolayan `pData` ve **pMgr** kendi ilgili üye değişkenlerine (`m_pData` ve **m_pMgr**). Ardından, sıfır olarak sabit arabellek ve başvuru sayısı-1 en büyük boyutuna eşit kullanılabilir uzunluğu arabellek uzunluğu ayarlar. Başvuru sayı değeri arabellek kilitli gösterir ve bu örneği kullanmak için **CFixedStringMgr** dize Yöneticisi olarak.  
  
 Arabellek kilitli olarak işaretleme, engeller diğer `CStringT` arabellek paylaşılan başvuru bulunduran gelen örnekleri. Başka `CStringT` örnekleri bu olacaktır tarafından bulunan arabellek için olası arabellek paylaşmak için izin verilen `CFixedStringT` diğer dizeleri arabellek kullanmaya devam sırada silinecek.  
  
 **CFixedStringMgr** tam bir uygulamasıdır `IAtlStringMgr` arabirimi. Her yöntemin kullanımı ayrı olarak ele alınmıştır.  
  
## <a name="implementation-of-cfixedstringmgrallocate"></a>CFixedStringMgr::Allocate uygulaması  
 Uygulaması **CFixedStringMgr::Allocate** dize istenen boyutu sabit arabellek boyutunu küçük veya buna eşit olup olmadığını görmek için ilk denetimleri (depolanan `m_pData` üyesi). Sabit arabellek yeteri kadar büyük olursa **CFixedStringMgr** sıfır uzunluğunda sabit arabellek kilitler. Dize uzunluğu sabit arabellek boyutu büyümesine değil sürece `CStringT` arabelleği yeniden ayırmak zorunda kalmazsınız.  
  
 Dize istenen boyutu sabit arabellekten daha büyük olup olmadığını **CFixedStringMgr** yedekleme dize Yöneticisi isteği iletir. Öbek arabelleğinden ayırmak için yedekleme dize Yöneticisi'ni kabul edilir. Ancak, bu arabellek dönmeden önce **CFixedStringMgr** arabellek kilitler ve arabellek dize Yöneticisi işaretçisi işaretçisi ile değiştirir **CFixedStringMgr** nesnesi. Bu denemelerinin yeniden ayırmak veya tarafından arabelleği serbest sağlar `CStringT` içine çağıracak **CFixedStringMgr**.  
  
## <a name="implementation-of-cfixedstringmgrreallocate"></a>CFixedStringMgr::ReAllocate uygulaması  
 Uygulaması **CFixedStringMgr::ReAllocate** kendi uygulamasına yönelik çok benzer **ayırma**.  
  
 Sabit arabellek yeniden tahsis arabellek ise ve istenen arabellek boyutu sabit arabellekten daha küçük, hiçbir ayırma yapılır. Ancak, yeniden tahsis arabellek sabit arabellek değilse yedekleme Yöneticisi ile ayrılan arabellek olması gerekir. Bu durumda yedekleme Yöneticisi'ni, arabellek yeniden ayırmak üzere kullanılır.  
  
 Yeniden tahsis arabellek sabit arabellek ve yeni arabellek boyutu sabit arabellek içinde sığmayacak kadar büyük ise **CFixedStringMgr** yedekleme Yöneticisi'ni kullanarak yeni bir arabellek ayırır. Sabit arabellek içeriğini sonra yeni arabelleğe kopyalanır.  
  
## <a name="implementation-of-cfixedstringmgrfree"></a>CFixedStringMgr::Free uygulaması  
 Uygulaması **CFixedStringMgr::Free** olarak aynı deseni takip **ayırma** ve `ReAllocate`. Bırakılan arabellek sabit arabellek ise, yöntem bir sıfır uzunluklu kilitli arabellek ayarlar. Bırakılan arabellek yedekleme Yöneticisi ile ayırdığınızda **CFixedStringMgr** onu boşaltmak için yedekleme Yöneticisi'ni kullanır.  
  
## <a name="implementation-of-cfixedstringmgrclone"></a>CFixedStringMgr::Clone uygulaması  
 Uygulaması **CFixedStringMgr::Clone** her zaman bir işaretçi yedekleme Yöneticisi'ni döndürür yerine **CFixedStringMgr** kendisi. Çünkü böyle her örneğinin **CFixedStringMgr** yalnızca tek bir örneği ile ilişkili olabilir `CStringT`. Diğer örneklerini `CStringT` Yöneticisi kopyalama girişiminde alma yedekleme Yöneticisi'ni yerine. Yedekleme Yöneticisi'ni paylaşılmasını destekleyen olmasıdır.  
  
## <a name="implementation-of-cfixedstringmgrgetnilstring"></a>CFixedStringMgr::GetNilString uygulaması  
 Uygulaması **CFixedStringMgr::GetNilString** sabit arabelleğini döndürür. Bire iletişimi nedeniyle **CFixedStringMgr** ve `CStringT`, belirli bir örneğini `CStringT` hiçbir zaman aynı anda birden fazla arabellek kullanır. Bu nedenle, boş bir dize ve gerçek dize arabellek hiçbir zaman aynı anda gereklidir.  
  
 Sabit Arabellek kullanımda değil her **CFixedStringMgr** sıfır uzunlukta başlatıldığını sağlar. Bu boş dize olarak kullanılmasını sağlar. Eklenen bir ödül olarak `nAllocLength` sabit arabellek üyesi tam sabit arabellek boyutu için her zaman ayarlayın. Bunun anlamı `CStringT` çağırmadan dize büyüyebilir [IAtlStringMgr::Reallocate](../atl-mfc-shared/reference/iatlstringmgr-class.md#reallocate)bile boş dize.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** cstringt.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CStringT ile Bellek Yönetimi](../atl-mfc-shared/memory-management-with-cstringt.md)

