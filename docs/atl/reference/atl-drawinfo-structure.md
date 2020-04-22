---
title: ATL_DRAWINFO Yapısı
ms.date: 11/04/2016
f1_keywords:
- ATL::ATL_DRAWINFO
- ATL_DRAWINFO
- ATL.ATL_DRAWINFO
helpviewer_keywords:
- ATL_DRAWINFO structure
ms.assetid: dd2e2aa8-e8c5-403b-b4df-35c0f6f57fb7
ms.openlocfilehash: fb50f49d387e8620f3d5bbb41263738adbd8b437
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81748797"
---
# <a name="atl_drawinfo-structure"></a>ATL_DRAWINFO Yapısı

Yazıcı, metadosya veya ActiveX denetimi gibi çeşitli hedeflere işlemek için kullanılan bilgileri içerir.

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

`cbSize`<br/>
Yapının büyüklüğü, baytlar halinde.

`dwDrawAspect`<br/>
Hedefin nasıl temsil edilebildiğini belirtir. Temsiller içerik, simge, küçük resim veya yazdırılmış bir belge içerebilir. Olası değerlerin listesi için [DVASPECT](/windows/win32/api/wtypes/ne-wtypes-dvaspect) ve [DVASPECT2'ye](/windows/win32/api/ocidl/ne-ocidl-dvaspect2)bakın.

`lindex`<br/>
Hedefin çekme işlemi için ilgi çeken kısmı. Yorumu üyenin değerine `dwDrawAspect` bağlı olarak değişir.

`ptd`<br/>
Belirtilen yöne bağlı olarak çizim optimizasyonları sağlayan bir [DVTARGETDEVICE](/windows/win32/api/objidl/ns-objidl-dvtargetdevice) yapısıişaretçisi. En iyi çizim arabirimlerini destekleyen yeni nesnelerin ve kapsayıcıların da bu üyeyi desteklediğini unutmayın. En iyi leştirilmiş çizim arabirimlerini desteklemeyen eski nesneler ve kapsayıcılar bu üye için her zaman NULL belirtir.

`hicTargetDev`<br/>
Nesnenin aygıt ölçümlerini ayıklayıp aygıtın yeteneklerini test edebileceği hedef aygıtın `ptd` bilgi bağlamı. NULL `ptd` ise, nesne `hicTargetDev` üyedeki değeri yok saymalıdır.

`hdcDraw`<br/>
Çizecek aygıt bağlamı. Penceresiz bir nesne `hdcDraw` için üye, `MM_TEXT` içeren pencerenin istemci koordinatlarıyla eşleşen mantıksal koordinatlarıyla eşleme modundadır. Buna ek olarak, aygıt bağlamı normalde bir `WM_PAINT` ileti tarafından geçirilen aynı durumda olmalıdır.

`prcBounds`<br/>
Dikdörtgeni ve nesnenin `hdcDraw` çizilmesi gerektiğini belirten [rectl](/windows/win32/api/windef/ns-windef-rectl) yapısına işaretçi. Bu üye nesnenin konumlandırılmasını ve uzasını denetler. Penceresiz bir etkin nesne çizmek için bu üye NULL olmalıdır. Diğer her durumda, NULL yasal bir değer değildir `E_INVALIDARG` ve bir hata kodu ile sonuçlanmalıdır. Kapsayıcı penceresiz bir nesneye NULL olmayan bir değer geçirirse, nesne istenen yönü belirtilen aygıt bağlamına ve dikdörtgenin içine girmelidir. Kapsayıcı, nesnenin ikinci, etkin olmayan görünümünü işlemek veya nesneyi yazdırmak için penceresiz bir nesneden bunu isteyebilir.

`prcWBounds`<br/>
Metadosya aygıt bağlamı `hdcDraw` ise (bkz. Windows SDK'daki [GetDeviceCaps),](/windows/win32/api/wingdi/nf-wingdi-getdevicecaps) bu, temel metadosyadaki sınırlayıcı dikdörtgeni belirten bir `RECTL` yapıya işaretçidir. Dikdörtgen yapısı pencere kapsamı ve pencere kökeni içerir. Bu değerler meta dosyaları çizmek için yararlıdır. Tarafından belirtilen dikdörtgen `prcBounds` bu `prcWBounds` dikdörtgenin içine iç içe; aynı koordinat alanındadırlar.

`bOptimize`<br/>
Sıfır olmayan denetim çizim, aksi takdirde 0 optimize edilecek. Çizim en iyi duruma getirilirse, işleme bittikten sonra aygıt bağlamının durumu otomatik olarak geri yüklenir.

`bZoomed`<br/>
Hedefin yakınlaştırma faktörü varsa sıfır yok, aksi takdirde 0. Yakınlaştırma faktörü `ZoomNum`.

`bRectInHimetric`<br/>
Boyutlar `prcBounds` HIMETRIC ise sıfır değil, aksi takdirde 0.

`ZoomNum`<br/>
Nesnenin işlendiği dikdörtgenin genişliği ve yüksekliği. Hedefin `ZoomNum.cx` x ekseni boyunca yakınlaştırma faktörü (nesnenin doğal boyutunun bugünkü boyutuna oranı) `ZoomDen.cx`. Y ekseni boyunca yakınlaştırma faktörü benzer bir şekilde elde edilir.

`ZoomDen`<br/>
Hedefin gerçek genişliği ve yüksekliği.

## <a name="remarks"></a>Açıklamalar

Bu yapının tipik kullanımı, hedef nesnenin işlenmesi sırasında bilgi alınması olacaktır. Örneğin, [CComControlBase::OnDrawAdvanced](ccomcontrolbase-class.md#ondrawadvanced)aşırı içinde ATL_DRAWINFO değerleri alabilirsiniz.

Bu yapı, hedef aygıt için bir nesnenin görünümünü işlemek için kullanılan ilgili bilgileri depolar. Sağlanan bilgiler ekrana, yazıcıya ve hatta bir meta dosyaya çizimde kullanılabilir.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlctl.h

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar ve structs](../../atl/reference/atl-classes.md)<br/>
[IViewObject::Draw](/windows/win32/api/oleidl/nf-oleidl-iviewobject-draw)<br/>
[CcomControlBase::OndrawAdvanced](../../atl/reference/ccomcontrolbase-class.md#ondrawadvanced)
