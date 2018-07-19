---
title: Atl_drawınfo yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fa45822d51d704022e773f6c8220db34b010a805
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/06/2018
ms.locfileid: "37885828"
---
# <a name="atldrawinfo-structure"></a>Atl_drawınfo yapısı
Bir yazıcı, meta dosyası ya da ActiveX denetimi gibi çeşitli hedeflere işleme için kullanılan bilgileri içerir.  
  
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
 Yapının bayt cinsinden boyutu.  
  
 `dwDrawAspect`  
 Nasıl gösterilemeyecek kadar hedef olduğunu belirtir. Gösterimleri, içerik, simge, küçük resim veya yazdırılan belge içerebilir. Olası değerler listesi için bkz. [DVASPECT](http://msdn.microsoft.com/library/windows/desktop/ms690318) ve [DVASPECT2](http://msdn.microsoft.com/library/windows/desktop/ms688644).  
  
 `lindex`  
 Çizim işlemi için hedef kısmı. Değerine bağlı olarak yorumlanması değişir `dwDrawAspect` üyesi.  
  
 `ptd`  
 İşaretçi bir [DVTARGETDEVICE](http://msdn.microsoft.com/library/windows/desktop/ms686613) belirtilen boyut bağlı olarak çizim iyileştirmelerini sağlayan yapısı. Yeni nesneleri ve en iyi duruma getirilmiş çizim arabirimleri destekleyen kapsayıcılar bu üyeyi de destekleyip desteklemediğini unutmayın. Eski nesneler ve her zaman en iyi duruma getirilmiş çizim arabirimleri desteklemeyen kapsayıcıları bu üye için NULL belirtin.  
  
 `hicTargetDev`  
 Hedef cihaz bağlamının bilgi tarafından işaret edilen `ptd` içinden nesne cihaz ölçümleri ayıklayın ve cihazın özelliklerini test edebilirsiniz. Varsa `ptd` null, nesne değeri sayılmalıdır `hicTargetDev` üyesi.  
  
 `hdcDraw`  
 Cihaz bağlamı üretileceği çizin. Penceresiz bir nesne için `hdcDraw` üyesiyse `MM_TEXT` pencerenin istemci koordinatları eşleşen mantıksal koordinatları ile eşleme modu. Ayrıca, cihaz bağlam normalde geçirilen aynı duruma olmalıdır bir `WM_PAINT` ileti.  
  
 `prcBounds`  
 İşaretçi bir [RECTL](http://msdn.microsoft.com/library/windows/desktop/dd162907) dikdörtgen belirterek yapısı `hdcDraw` ve nesne çizileceğini. Bu üye, konumlandırma ve nesnenin uzatma denetler. Bu üye penceresiz yerinde etkin nesne çizmek için NULL olmalıdır. Diğer her durumda, NULL geçerli bir değer değil ve neden bir `E_INVALIDARG` hata kodu. Kapsayıcı penceresiz bir nesne için bir NULL olmayan değer geçerse, nesne dikdörtgen ve belirtilen bir cihaz bağlamı içinde istenen boyut işlemesi gerekir. Bir kapsayıcı bir penceresiz nesneden nesnesinin ikinci, etkin olmayan görünüm işlemek için veya nesneyi yazdırmak için bu talep edebilir.  
  
 `prcWBounds`  
 Varsa `hdcDraw` bir meta dosyası cihaz bağlamı (bkz [GetDeviceCaps](http://msdn.microsoft.com/library/windows/desktop/dd144877) Windows SDK), bu işaretçisidir bir `RECTL` yapısı temel alınan meta sınırlayıcı belirtme. Dikdörtgen yapı penceresi başlangıç ve pencere uzantı içeriyor. Bu değerler, meta çizmek için yararlıdır. Tarafından belirtilen dikdörtgen `prcBounds` bu iç içe geçmiş `prcWBounds` dikdörtgen; aynı koordinat alanında oldukları.  
  
 `bOptimize`  
 Çizim denetimi olacak şekilde iyileştirilmiştir, aksi durumda 0 ise sıfır olmayan. Çizim en iyi duruma getirilmiş işiniz bittiğinde durumu cihaz bağlamı otomatik olarak geri yüklenir işleme.  
  
 `bZoomed`  
 Aksi durumda 0 yakınlaştırma faktörünü hedefi varsa, sıfır dışında. Yakınlaştırma faktörünü depolanan `ZoomNum`.  
  
 `bRectInHimetric`  
 Gösterimiyse boyutlarını `prcBounds` HIMETRIC, aksi durumda 0 olan.  
  
 `ZoomNum`  
 Genişlik ve yükseklik dikdörtgenin içine bir nesne oluşturulur. Yakınlaştırma faktörünü hedefinin (nesnenin geçerli kapsamı doğal boyutuna oranı) x ekseni boyunca değeri `ZoomNum.cx` değeriyle bölünmüş `ZoomDen.cx`. Yakınlaştırma faktörünü y ekseni boyunca benzer şekilde sağlanır.  
  
 `ZoomDen`  
 Gerçek genişlik ve yükseklik hedef.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yapının tipik kullanım hedef nesnenin işleme sırasında bilgilerin alınmasını olacaktır. Örneğin, değerleri atl_drawınfo, aşırı yüklemesini içinde alabilir [CComControlBase::OnDrawAdvanced](ccomcontrolbase-class.md#ondrawadvanced).  
  
 Bu yapı, hedef cihaz için bir nesnenin görünümü işlemek için kullanılan bilgileri depolar. Çizim ekran, yazıcı veya hatta bir meta dosyası içinde sağlanan bilgileri kullanılabilir.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlctl.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
  [Sınıflar ve yapılar](../../atl/reference/atl-classes.md) [IViewObject::Draw](http://msdn.microsoft.com/library/windows/desktop/ms688655)   
 [CComControlBase::OnDrawAdvanced](../../atl/reference/ccomcontrolbase-class.md#ondrawadvanced)





