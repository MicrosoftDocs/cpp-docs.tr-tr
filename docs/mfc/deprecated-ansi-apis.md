---
description: "Daha fazla bilgi edinin: kullanım dışı ANSI API 'Leri"
title: Kullanım Dışı ANSI API'ları
ms.date: 11/04/2016
helpviewer_keywords:
- MFC, ANSI deprecated methods
ms.assetid: c7c5a6fd-95e4-4bee-b3d5-d3826c30947d
ms.openlocfilehash: b709e67a032a25335fe6d05b3662db264232193c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97290992"
---
# <a name="deprecated-ansi-apis"></a>Kullanım Dışı ANSI API'ları

Microsoft Foundation Class (MFC) kitaplığı, Unicode karakter kümesini temel alan sınıflara ve yöntemlere doğru geçiriliyor. Sonuç olarak, birkaç MFC yönteminin ANSI sürümleri kullanım dışıdır. Gelecekteki uygulamalarınızda bu yöntemlerin Unicode sürümlerini kullanın.

Windows Vista 'da sunulan Windows ortak denetimleri sürüm 6,1 ' den başlayarak, aşağıdaki ANSI yöntemleri kullanım dışıdır.

## <a name="cbutton-class"></a>CButton sınıfı

```
AFX_ANSI_DEPRECATED BOOL GetIdealSize(LPSIZE psize) const;

AFX_ANSI_DEPRECATED BOOL GetImageList(PBUTTON_IMAGELIST pbuttonImagelist) const;

AFX_ANSI_DEPRECATED BOOL GetTextMargin(LPRECT pmargin) const;

AFX_ANSI_DEPRECATED BOOL SetImageList(PBUTTON_IMAGELIST pbuttonImagelist);

AFX_ANSI_DEPRECATED BOOL SetTextMargin(LPRECT pmargin);
```

## <a name="ccomboboxex-class"></a>CComboBoxEx sınıfı

```
AFX_ANSI_DEPRECATED HRESULT SetWindowTheme(LPCWSTR pszSubAppName);
```

## <a name="cedit-class"></a>CEdit sınıfı

```
AFX_ANSI_DEPRECATED BOOL GetCueBanner(LPWSTR lpszText,
    int cchText) const;

AFX_ANSI_DEPRECATED BOOL SetCueBanner(LPCWSTR lpszText,
    BOOL fDrawIfFocused = FALSE);
```

## <a name="clinkctrl-class"></a>CLinkCtrl sınıfı

Tüm sınıf kullanım dışıdır.

## <a name="clistctrl-class"></a>CListCtrl sınıfı

```
AFX_ANSI_DEPRECATED void CancelEditLabel();

AFX_ANSI_DEPRECATED int EnableGroupView(BOOL fEnable);

AFX_ANSI_DEPRECATED int GetGroupInfo(int iGroupId,
    PLVGROUP pgrp) const;

AFX_ANSI_DEPRECATED void GetGroupMetrics(PLVGROUPMETRICS pGroupMetrics) const;

AFX_ANSI_DEPRECATED BOOL GetInsertMark(LPLVINSERTMARK lvim) const;

AFX_ANSI_DEPRECATED COLORREF GetInsertMarkColor() const;

AFX_ANSI_DEPRECATED int GetInsertMarkRect(LPRECT pRect) const;

AFX_ANSI_DEPRECATED COLORREF GetOutlineColor() const;

AFX_ANSI_DEPRECATED UINT GetSelectedColumn() const;

AFX_ANSI_DEPRECATED BOOL GetTileInfo(PLVTILEINFO pti) const;

AFX_ANSI_DEPRECATED BOOL GetTileViewInfo(PLVTILEVIEWINFO ptvi) const;

AFX_ANSI_DEPRECATED DWORD GetView() const;

AFX_ANSI_DEPRECATED BOOL HasGroup(int iGroupId) const;

AFX_ANSI_DEPRECATED int InsertGroup(int index,
    PLVGROUP pgrp);

AFX_ANSI_DEPRECATED void InsertGroupSorted(PLVINSERTGROUPSORTED pStructInsert);

AFX_ANSI_DEPRECATED int InsertMarkHitTest(LPPOINT pPoint,
    LPLVINSERTMARK lvim) const;

AFX_ANSI_DEPRECATED BOOL IsGroupViewEnabled() const;

AFX_ANSI_DEPRECATED void MoveGroup(int iGroupId,
    int toIndex);

AFX_ANSI_DEPRECATED void MoveItemToGroup(int idItemFrom,
    int idGroupTo);

AFX_ANSI_DEPRECATED void RemoveAllGroups();

AFX_ANSI_DEPRECATED int RemoveGroup(int iGroupId);

AFX_ANSI_DEPRECATED BOOL SetGroupInfo(int iGroupId,
    PLVGROUP pGroup);

AFX_ANSI_DEPRECATED void SetGroupMetrics(PLVGROUPMETRICS pGroupMetrics);

AFX_ANSI_DEPRECATED BOOL SetInfoTip(PLVSETINFOTIP plvInfoTip);

AFX_ANSI_DEPRECATED BOOL SetInsertMark(LPLVINSERTMARK lvim);

AFX_ANSI_DEPRECATED COLORREF SetInsertMarkColor(COLORREF color);

AFX_ANSI_DEPRECATED COLORREF SetOutlineColor(COLORREF color);

AFX_ANSI_DEPRECATED void SetSelectedColumn(int iCol);

AFX_ANSI_DEPRECATED BOOL SetTileInfo(PLVTILEINFO pti);

AFX_ANSI_DEPRECATED BOOL SetTileViewInfo(PLVTILEVIEWINFO ptvi);

AFX_ANSI_DEPRECATED DWORD SetView(int iView);

AFX_ANSI_DEPRECATED BOOL SortGroups(PFNLVGROUPCOMPARE _pfnGroupCompare,
    LPVOID _plv);
```

## <a name="crebarctrl-class"></a>CReBarCtrl sınıfı

```
AFX_ANSI_DEPRECATED void GetBandMargins(PMARGINS pMargins) const;

AFX_ANSI_DEPRECATED HRESULT SetWindowTheme(LPCWSTR pszSubAppName);
```

## <a name="ctoolbarctrl-class"></a>CToolBarCtrl sınıfı

```
AFX_ANSI_DEPRECATED void GetMetrics(LPTBMETRICS ptbm) const;

AFX_ANSI_DEPRECATED void SetMetrics(LPTBMETRICS ptbm);

AFX_ANSI_DEPRECATED HRESULT SetWindowTheme(LPCWSTR pszSubAppName);
```

## <a name="ctooltipctrl-class"></a>CToolTipCtrl sınıfı

```
AFX_ANSI_DEPRECATED HRESULT SetWindowTheme(LPCWSTR pszSubAppName);
```

## <a name="see-also"></a>Ayrıca bkz.

[Windows Vista ortak denetimleri için derleme gereksinimleri](build-requirements-for-windows-vista-common-controls.md)
