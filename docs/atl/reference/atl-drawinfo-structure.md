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
ms.openlocfilehash: 00d93b3dd8b060a21b6ff4083bb9880d8d836a19
ms.sourcegitcommit: 2bc15c5b36372ab01fa21e9bcf718fa22705814f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/27/2020
ms.locfileid: "82168624"
---
# <a name="atl_drawinfo-structure"></a>ATL_DRAWINFO Yapısı

Bir yazıcı, meta dosya veya ActiveX denetimi gibi çeşitli hedeflere işleme için kullanılan bilgileri içerir.

## <a name="syntax"></a>Sözdizimi

```cpp
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
Yapının bayt cinsinden boyutu.

`dwDrawAspect`<br/>
Hedefin nasıl temsil edileceğini belirtir. Temsiller, içerik, simge, küçük resim veya yazdırılmış bir belge içerebilir. Olası değerler listesi için bkz. [DVASPECT](/windows/win32/api/wtypes/ne-wtypes-dvaspect) ve [DVASPECT2](/windows/win32/api/ocidl/ne-ocidl-dvaspect2).

`lindex`<br/>
Hedefin, çizim işleminin ilgilendiği kısmı. Yorumu, `dwDrawAspect` üyenin değerine bağlı olarak değişir.

`ptd`<br/>
Belirtilen değere bağlı olarak en iyi duruma getirme imkanı sağlayan bir [Dvtargetdevice](/windows/win32/api/objidl/ns-objidl-dvtargetdevice) yapısına yönelik işaretçi. İyileştirilmiş çizim arabirimlerini destekleyen yeni nesne ve kapsayıcıların bu üyeyi de desteklediğini unutmayın. En iyi duruma getirilmiş çizim arabirimlerini desteklemeyen eski nesneler ve kapsayıcılar, bu üye için her zaman NULL değer belirtir.

`hicTargetDev`<br/>
Tarafından `ptd` işaret edilen hedef cihaz için, nesnenin cihaz ölçümlerini ayıklayabileceği ve cihazın yeteneklerini test eden bilgi bağlamı. NULL `ptd` ise, nesne `hicTargetDev` üye içindeki değeri yok saymalıdır.

`hdcDraw`<br/>
Üzerine çizilecek cihaz bağlamı. Penceresiz bir nesne için `hdcDraw` üye, kapsayan pencerenin istemci koordinatlarıyla eşleşen mantıksal koordinatlarıyla `MM_TEXT` eşleme modundadır. Buna ek olarak, cihaz bağlamı, normalde bir `WM_PAINT` ileti tarafından geçirildiği ile aynı durumda olmalıdır.

`prcBounds`<br/>
Üzerinde `hdcDraw` nesnenin çizilmesi gereken dikdörtgeni belirten [rectl](/windows/win32/api/windef/ns-windef-rectl) yapısına yönelik işaretçi. Bu üye nesnenin konumlandırılmasını ve uzamasını denetler. Bu üye, bir penceresiz yerinde etkin nesne çizmek için NULL olmalıdır. Her durumda NULL değeri geçerli bir değer değildir ve bir `E_INVALIDARG` hata kodu ile sonuçlanmalıdır. Kapsayıcı, penceresiz bir nesneye NULL olmayan bir değer geçirirse, nesne istenen yönü belirtilen cihaz bağlamı ve dikdörtgenine işlemelidir. Bir kapsayıcı, nesnenin ikinci, etkin olmayan bir görünümünü işlemek veya nesneyi yazdırmak için bunu penceresiz bir nesneden isteyebilir.

`prcWBounds`<br/>
Bir meta dosyası cihaz bağlamıdır (bkz. Windows SDK [GetDeviceCaps](/windows/win32/api/wingdi/nf-wingdi-getdevicecaps) ), bu, temel alınan meta dosyasındaki sınırlayıcı `RECTL` dikdörtgeni belirten bir yapıya işaretçidir. `hdcDraw` Dikdörtgen yapısı pencere kapsamı ve pencere kaynağını içerir. Bu değerler, meta dosyaları çizmek için yararlıdır. Tarafından `prcBounds` belirtilen dikdörtgen, bu `prcWBounds` dikdörtgenin içinde iç içe yerleştirilmiş. aynı koordinat alanında yer alırlar.

`bOptimize`<br/>
Denetimin çizimi iyileştirilemez, aksi durumda 0. Çizim iyileştiriliyorsa, işleme işiniz bittiğinde cihaz bağlamının durumu otomatik olarak geri yüklenir.

`bZoomed`<br/>
Hedefte bir yakınlaştırma faktörü varsa sıfır dışı, aksi durumda 0. Yakınlaştırma faktörü içinde `ZoomNum`depolanır.

`bRectInHimetric`<br/>
Boyutlar `prcBounds` himetrik ise, aksi durumda 0.

`ZoomNum`<br/>
Nesnenin işlendiği dikdörtgenin genişliği ve yüksekliği. Hedef değerinin x ekseni (nesnenin doğal boyutunun geçerli adına göre oranı) üzerindeki yakınlaştırma faktörü, değerine `ZoomNum.cx` bölünen değeridir. `ZoomDen.cx` Y ekseni üzerindeki yakınlaştırma faktörü benzer bir biçimde elde edilir.

`ZoomDen`<br/>
Hedefin gerçek genişliği ve yüksekliği.

## <a name="remarks"></a>Açıklamalar

Bu yapının tipik kullanımı, hedef nesnenin işlenmesi sırasında bilgilerin alınması olacaktır. Örneğin, [CComControlBase:: OnDrawAdvanced](ccomcontrolbase-class.md#ondrawadvanced)öğesinin aşırı yüklerinizin içindeki ATL_DRAWINFO değerler alabilirsiniz.

Bu yapı, hedef cihaz için bir nesnenin görünümünü işlemek üzere kullanılan ilgili bilgileri depolar. Girilen bilgiler, ekranda, yazıcıda veya hatta bir meta dosyasına çizimde kullanılabilir.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlctl. h

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar ve yapılar](../../atl/reference/atl-classes.md)<br/>
[IViewObject::D RAW](/windows/win32/api/oleidl/nf-oleidl-iviewobject-draw)<br/>
[CComControlBase:: OnDrawAdvanced](../../atl/reference/ccomcontrolbase-class.md#ondrawadvanced)
