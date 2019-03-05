---
title: Atl_drawınfo yapısı
ms.date: 11/04/2016
f1_keywords:
- ATL::ATL_DRAWINFO
- ATL_DRAWINFO
- ATL.ATL_DRAWINFO
helpviewer_keywords:
- ATL_DRAWINFO structure
ms.assetid: dd2e2aa8-e8c5-403b-b4df-35c0f6f57fb7
ms.openlocfilehash: 70329d3b2c18c8cd8e94854f40ff971c0b39a8f4
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57301824"
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

`cbSize`<br/>
Yapının bayt cinsinden boyutu.

`dwDrawAspect`<br/>
Nasıl gösterilemeyecek kadar hedef olduğunu belirtir. Gösterimleri, içerik, simge, küçük resim veya yazdırılan belge içerebilir. Olası değerler listesi için bkz. [DVASPECT](/windows/desktop/api/wtypes/ne-wtypes-tagdvaspect) ve [DVASPECT2](/windows/desktop/api/ocidl/ne-ocidl-tagdvaspect2).

`lindex`<br/>
Çizim işlemi için hedef kısmı. Değerine bağlı olarak yorumlanması değişir `dwDrawAspect` üyesi.

`ptd`<br/>
İşaretçi bir [DVTARGETDEVICE](/windows/desktop/api/objidl/ns-objidl-tagdvtargetdevice) belirtilen boyut bağlı olarak çizim iyileştirmelerini sağlayan yapısı. Yeni nesneleri ve en iyi duruma getirilmiş çizim arabirimleri destekleyen kapsayıcılar bu üyeyi de destekleyip desteklemediğini unutmayın. Eski nesneler ve her zaman en iyi duruma getirilmiş çizim arabirimleri desteklemeyen kapsayıcıları bu üye için NULL belirtin.

`hicTargetDev`<br/>
Hedef cihaz bağlamının bilgi tarafından işaret edilen `ptd` içinden nesne cihaz ölçümleri ayıklayın ve cihazın özelliklerini test edebilirsiniz. Varsa `ptd` null, nesne değeri sayılmalıdır `hicTargetDev` üyesi.

`hdcDraw`<br/>
Cihaz bağlamı üretileceği çizin. Penceresiz bir nesne için `hdcDraw` üyesiyse `MM_TEXT` pencerenin istemci koordinatları eşleşen mantıksal koordinatları ile eşleme modu. Ayrıca, cihaz bağlam normalde geçirilen aynı duruma olmalıdır bir `WM_PAINT` ileti.

`prcBounds`<br/>
İşaretçi bir [RECTL](https://msdn.microsoft.com/library/windows/desktop/dd162907) dikdörtgen belirterek yapısı `hdcDraw` ve nesne çizileceğini. Bu üye, konumlandırma ve nesnenin uzatma denetler. Bu üye penceresiz yerinde etkin nesne çizmek için NULL olmalıdır. Diğer her durumda, NULL geçerli bir değer değil ve neden bir `E_INVALIDARG` hata kodu. Kapsayıcı penceresiz bir nesne için bir NULL olmayan değer geçerse, nesne dikdörtgen ve belirtilen bir cihaz bağlamı içinde istenen boyut işlemesi gerekir. Bir kapsayıcı bir penceresiz nesneden nesnesinin ikinci, etkin olmayan görünüm işlemek için veya nesneyi yazdırmak için bu talep edebilir.

`prcWBounds`<br/>
Varsa `hdcDraw` bir meta dosyası cihaz bağlamı (bkz [GetDeviceCaps](/windows/desktop/api/wingdi/nf-wingdi-getdevicecaps) Windows SDK), bu işaretçisidir bir `RECTL` yapısı temel alınan meta sınırlayıcı belirtme. Dikdörtgen yapı penceresi başlangıç ve pencere uzantı içeriyor. Bu değerler, meta çizmek için yararlıdır. Tarafından belirtilen dikdörtgen `prcBounds` bu iç içe geçmiş `prcWBounds` dikdörtgen; aynı koordinat alanında oldukları.

`bOptimize`<br/>
Çizim denetimi olacak şekilde iyileştirilmiştir, aksi durumda 0 ise sıfır olmayan. Çizim en iyi duruma getirilmiş işiniz bittiğinde durumu cihaz bağlamı otomatik olarak geri yüklenir işleme.

`bZoomed`<br/>
Aksi durumda 0 yakınlaştırma faktörünü hedefi varsa, sıfır dışında. Yakınlaştırma faktörünü depolanan `ZoomNum`.

`bRectInHimetric`<br/>
Gösterimiyse boyutlarını `prcBounds` HIMETRIC, aksi durumda 0 olan.

`ZoomNum`<br/>
Genişlik ve yükseklik dikdörtgenin içine bir nesne oluşturulur. Yakınlaştırma faktörünü hedefinin (nesnenin geçerli kapsamı doğal boyutuna oranı) x ekseni boyunca değeri `ZoomNum.cx` değeriyle bölünmüş `ZoomDen.cx`. Yakınlaştırma faktörünü y ekseni boyunca benzer şekilde sağlanır.

`ZoomDen`<br/>
Gerçek genişlik ve yükseklik hedef.

## <a name="remarks"></a>Açıklamalar

Bu yapının tipik kullanım hedef nesnenin işleme sırasında bilgilerin alınmasını olacaktır. Örneğin, değerleri atl_drawınfo, aşırı yüklemesini içinde alabilir [CComControlBase::OnDrawAdvanced](ccomcontrolbase-class.md#ondrawadvanced).

Bu yapı, hedef cihaz için bir nesnenin görünümü işlemek için kullanılan bilgileri depolar. Çizim ekran, yazıcı veya hatta bir meta dosyası içinde sağlanan bilgileri kullanılabilir.

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlctl.h

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar ve yapılar](../../atl/reference/atl-classes.md)<br/>
[IViewObject::Draw](/windows/desktop/api/oleidl/nf-oleidl-iviewobject-draw)<br/>
[CComControlBase::OnDrawAdvanced](../../atl/reference/ccomcontrolbase-class.md#ondrawadvanced)
