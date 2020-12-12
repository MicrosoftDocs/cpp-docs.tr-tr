---
description: 'Daha fazla bilgi edinin: ATL_DRAWINFO yapısı'
title: ATL_DRAWINFO yapısı
ms.date: 11/04/2016
f1_keywords:
- ATL::ATL_DRAWINFO
- ATL_DRAWINFO
- ATL.ATL_DRAWINFO
helpviewer_keywords:
- ATL_DRAWINFO structure
ms.assetid: dd2e2aa8-e8c5-403b-b4df-35c0f6f57fb7
ms.openlocfilehash: 726a5b86f5621eba51d84054c80553b5c2f1f928
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97165400"
---
# <a name="atl_drawinfo-structure"></a>ATL_DRAWINFO yapısı

Bir yazıcı, meta dosya veya ActiveX denetimi gibi çeşitli hedeflere işleme için kullanılan bilgileri içerir.

## <a name="syntax"></a>Syntax

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
Hedefin, çizim işleminin ilgilendiği kısmı. Yorumu, üyenin değerine bağlı olarak değişir `dwDrawAspect` .

`ptd`<br/>
Belirtilen değere bağlı olarak en iyi duruma getirme imkanı sağlayan bir [Dvtargetdevice](/windows/win32/api/objidl/ns-objidl-dvtargetdevice) yapısına yönelik işaretçi. İyileştirilmiş çizim arabirimlerini destekleyen yeni nesne ve kapsayıcıların bu üyeyi de desteklediğini unutmayın. En iyi duruma getirilmiş çizim arabirimlerini desteklemeyen eski nesneler ve kapsayıcılar, bu üye için her zaman NULL değer belirtir.

`hicTargetDev`<br/>
Tarafından işaret edilen hedef cihaz için `ptd` , nesnenin cihaz ölçümlerini ayıklayabileceği ve cihazın yeteneklerini test eden bilgi bağlamı. `ptd`Null ise, nesne üye içindeki değeri yok saymalıdır `hicTargetDev` .

`hdcDraw`<br/>
Üzerine çizilecek cihaz bağlamı. Penceresiz bir nesne için üye, `hdcDraw` `MM_TEXT` kapsayan pencerenin istemci koordinatlarıyla eşleşen mantıksal koordinatlarıyla eşleme modundadır. Buna ek olarak, cihaz bağlamı, normalde bir ileti tarafından geçirildiği ile aynı durumda olmalıdır `WM_PAINT` .

`prcBounds`<br/>
Üzerinde nesnenin çizilmesi gereken dikdörtgeni belirten [rectl](/windows/win32/api/windef/ns-windef-rectl) yapısına yönelik işaretçi `hdcDraw` . Bu üye nesnenin konumlandırılmasını ve uzamasını denetler. Bu üye, bir penceresiz yerinde etkin nesne çizmek için NULL olmalıdır. Her durumda NULL değeri geçerli bir değer değildir ve bir hata kodu ile sonuçlanmalıdır `E_INVALIDARG` . Kapsayıcı, penceresiz bir nesneye NULL olmayan bir değer geçirirse, nesne istenen yönü belirtilen cihaz bağlamı ve dikdörtgenine işlemelidir. Bir kapsayıcı, nesnenin ikinci, etkin olmayan bir görünümünü işlemek veya nesneyi yazdırmak için bunu penceresiz bir nesneden isteyebilir.

`prcWBounds`<br/>
`hdcDraw`Bir meta dosyası cihaz bağlamıdır (bkz. Windows SDK [GetDeviceCaps](/windows/win32/api/wingdi/nf-wingdi-getdevicecaps) ), bu, `RECTL` temel alınan meta dosyasındaki sınırlayıcı dikdörtgeni belirten bir yapıya işaretçidir. Dikdörtgen yapısı pencere kapsamı ve pencere kaynağını içerir. Bu değerler, meta dosyaları çizmek için yararlıdır. Tarafından belirtilen dikdörtgen `prcBounds` Bu dikdörtgenin içinde iç içe yerleştirilmiş `prcWBounds` ; aynı koordinat alanında yer alırlar.

`bOptimize`<br/>
Denetimin çizimi iyileştirilemez, aksi durumda 0. Çizim iyileştiriliyorsa, işleme işiniz bittiğinde cihaz bağlamının durumu otomatik olarak geri yüklenir.

`bZoomed`<br/>
Hedefte bir yakınlaştırma faktörü varsa sıfır dışı, aksi durumda 0. Yakınlaştırma faktörü içinde depolanır `ZoomNum` .

`bRectInHimetric`<br/>
Boyutlar `prcBounds` HIMETRIK ise, aksi durumda 0.

`ZoomNum`<br/>
Nesnenin işlendiği dikdörtgenin genişliği ve yüksekliği. Hedef değerinin x ekseni (nesnenin doğal boyutunun geçerli adına göre oranı) üzerindeki yakınlaştırma faktörü, `ZoomNum.cx` değerine bölünen değeridir `ZoomDen.cx` . Y ekseni üzerindeki yakınlaştırma faktörü benzer bir biçimde elde edilir.

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
