---
title: "ATL_DRAWINFO yapısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::ATL_DRAWINFO
- ATL_DRAWINFO
- ATL.ATL_DRAWINFO
dev_langs:
- C++
helpviewer_keywords:
- ATL_DRAWINFO structure
ms.assetid: dd2e2aa8-e8c5-403b-b4df-35c0f6f57fb7
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f7a10932fd43e89af6d98d3d931d43810c710000
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="atldrawinfo-structure"></a>ATL_DRAWINFO yapısı
Yazıcı, meta dosyası veya ActiveX denetimi gibi çeşitli hedeflere işleme için kullanılan bilgileri içerir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
struct ATL_DRAWINFO {
    UINT cbSize;
    DWORD dwDrawAspect;
    LONG lindex;
    DVTARGETDEVICE* ptd;
    HDC hicTargetDev;
    HDC hdcDraw;
    LPCRECTL prcBounds;
    LPCRECTL prcWBounds;
    BOOL bOptimize;
    BOOL bZoomed;
    BOOL bRectInHimetric;
    SIZEL ZoomNum;
    SIZEL ZoomDen;
};
```  
  
## <a name="members"></a>Üyeler  
 `cbSize`  
 Yapısı bayt cinsinden boyutu.  
  
 **dwDrawAspect**  
 Nasıl hedef gösterilemeyecek kadar belirtir. Beyanları içeriği, bir simge, bir küçük resim veya yazdırılan bir belge ekleyebilirsiniz. Olası değerler listesi için bkz: [DVASPECT](http://msdn.microsoft.com/library/windows/desktop/ms690318) ve [DVASPECT2](http://msdn.microsoft.com/library/windows/desktop/ms688644).  
  
 **lindex**  
 Çizim işlemi için ilgi hedef bölümü. Kendi yorumlama değeri bağlı olarak değişir **dwDrawAspect** üyesi.  
  
 **ptd**  
 İşaretçi bir [DVTARGETDEVICE](http://msdn.microsoft.com/library/windows/desktop/ms686613) yapısı belirtilen boyut bağlı olarak çizim iyileştirmeler sağlar. Yeni nesneleri ve Destek en iyi duruma getirilmiş çizim arabirimler kapsayıcıları bu üyeyi de desteklediğini unutmayın. Eski nesneler ve en iyi duruma getirilmiş çizim arabirimleri her zaman desteklemez kapsayıcıları belirtin **NULL** bu üye için.  
  
 **hicTargetDev**  
 Tarafından için bilgi bağlamı hedef cihaz için işaret **ptd** içinden nesne aygıt ölçümleri ayıklamak ve aygıtın özelliklerini test kullanabilirsiniz. Varsa **ptd** olan **NULL**, nesne değeri yok saymanız gerekir **hicTargetDev** üyesi.  
  
 **hdcDraw**  
 Cihaz bağlamı üretileceği çizin. Penceresiz bir nesne için **hdcDraw** üye olduğu `MM_TEXT` içeren pencere istemci koordinatları eşleşen mantıksal koordinatları ile eşleme modu. Ayrıca, cihaz bağlamı normalde geçirilen biri ile aynı duruma olması gerektiğini bir `WM_PAINT` ileti.  
  
 **prcBounds**  
 İşaretçi bir [RECTL](http://msdn.microsoft.com/library/windows/desktop/dd162907) Dikdörtgen Belirtme yapısı **hdcDraw** ve nesne çizileceğini. Bu üye konumlandırma ve nesnesinin uzatma denetler. Bu üye olmalıdır **NULL** penceresiz bir yerinde etkin nesne çizmek için. Diğer her durumda **NULL** geçerli bir değer değildir ve neden bir `E_INVALIDARG` hata kodu. Kapsayıcı olmayan bir geçerse**NULL** penceresiz bir nesne, nesne değerine dikdörtgen ve belirtilen cihaz bağlamı istenen boyut işleme. Bir kapsayıcı bu bir penceresiz nesneden nesnenin ikinci, etkin olmayan bir görünümü işlemek için veya nesneyi yazdırmak için isteyebilir.  
  
 **prcWBounds**  
 Varsa **hdcDraw** meta dosyası cihaz bağlamı (bkz [GetDeviceCaps](http://msdn.microsoft.com/library/windows/desktop/dd144877) Windows SDK'sındaki), bu gösteren bir işaretçidir bir **RECTL** sınırlayıcı dikdörtgenini belirtme yapısı temel alınan meta dosyası. Dikdörtgen yapı penceresi kapsamını ve penceresi kaynak içeriyor. Bu değerler, meta dosyaları çizim için yararlıdır. Dikdörtgen belirtilen tarafından **prcBounds** bu içinde iç içe geçmiş **prcWBounds** dikdörtgen; aynı koordinat alanında oldukları.  
  
 **bOptimize**  
 Denetim çizimini olması için en iyi duruma getirilmiş, aksi takdirde 0 ise sıfır olmayan. Çizim en iyi duruma getirilmiş, işiniz bittiğinde cihaz bağlamı durumunu otomatik olarak geri işleme.  
  
 **bZoomed**  
 Aksi halde 0 yakınlaştırma faktörünü hedef varsa, sıfır olmayan. Yakınlaştırma faktörünü depolanan **ZoomNum**.  
  
 **bRectInHimetric**  
 Sıfır olmayan IF boyutlarını **prcBounds** bulunan **HIMETRIC**, aksi halde 0.  
  
 **ZoomNum**  
 Genişlik ve yükseklik içine nesnesinin oluşturulması dikdörtgenin. Yakınlaştırma faktörünü hedef (nesnenin doğal boyutu, geçerli ölçüde oranını) x ekseni boyunca değeri **ZoomNum.cx** değeriyle bölünmüş **ZoomDen.cx**. Yakınlaştırma faktörünü y ekseni boyunca benzer bir şekilde elde edilir.  
  
 **ZoomDen**  
 Gerçek genişlik ve yükseklik hedef.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yapının tipik kullanım bilgileri hedef nesne oluşturma sırasında alınmasını olacaktır. Örneğin, değerleri alınamadı `ATL_DRAWINFO` aşırı yüklemesini içinde [CComControlBase::OnDrawAdvanced](ccomcontrolbase-class.md#ondrawadvanced).  
  
 Bu yapı hedef aygıt için bir nesne görünümünü işlemek için kullanılan bilgileri depolar. Sağlanan bilgiler, çizimdeki ekran, yazıcı veya hatta meta dosyası için kullanılabilir.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlctl.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapıları](../../atl/reference/atl-structures.md)   
 [IViewObject::Draw](http://msdn.microsoft.com/library/windows/desktop/ms688655)   
 [CComControlBase::OnDrawAdvanced](../../atl/reference/ccomcontrolbase-class.md#ondrawadvanced)





