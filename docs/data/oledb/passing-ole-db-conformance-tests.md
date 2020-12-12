---
description: 'Daha fazla bilgi edinin: OLE DB uygunluk testlerini geçirme'
title: OLE DB Uygunluk Testlerini Geçme
ms.date: 11/04/2016
helpviewer_keywords:
- testing, OLE DB providers
- testing providers
- conformance testing
- conformance testing [OLE DB]
- OLE DB providers, testing
ms.assetid: d1a4f147-2edd-476c-b452-0e6a0ac09891
ms.openlocfilehash: d2a5b788b3a118293800b02a9383fbde9845cfa5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97286729"
---
# <a name="passing-ole-db-conformance-tests"></a>OLE DB Uygunluk Testlerini Geçme

Sağlayıcıları daha tutarlı hale getirmek için, veri erişim SDK 'Sı bir OLE DB uygunluk testi kümesi sağlar. Testler sağlayıcınızın tüm yönlerini denetler ve sağlayıcınızın beklendiği gibi işlev görür. OLE DB uyumluluk testlerini Microsoft veri erişimi SDK 'sında bulabilirsiniz. Bu bölüm, uyumluluk testlerini geçirmek için yapmanız gereken şeylere odaklanmaktadır. OLE DB uygunluk testlerini çalıştırma hakkında daha fazla bilgi için bkz. SDK.

## <a name="running-the-conformance-tests"></a>Uygunluk testlerini çalıştırma

Visual C++ 6,0 ' de, OLE DB sağlayıcı şablonları değerleri ve özellikleri kontrol etmek için bir dizi ekleme işlevi eklemiştir. Bu işlevlerin çoğu, uygunluk testlerine yanıt olarak eklenmiştir.

> [!NOTE]
> Sağlayıcınızın OLE DB uygunluk testlerini geçirmesi için birkaç doğrulama işlevi eklemeniz gerekir.

Bu sağlayıcı iki doğrulama yordamı gerektirir. İlk yordam, `CRowsetImpl::ValidateCommandID` satır kümesi sınıfınızın bir parçasıdır. Sağlayıcı şablonları tarafından satır kümesi oluşturma sırasında çağrılır. Örnek, tüketicilere dizinleri desteklemediğini söylemek için bu yordamı kullanır. İlk çağrı `CRowsetImpl::ValidateCommandID` ' dır (sağlayıcının, `_RowsetBaseClass` `CCustomRowset` [yer işaretleri için sağlayıcı desteği](../../data/oledb/provider-support-for-bookmarks.md)için arabirim eşlemesinde eklenen typedef 'i kullandığını unutmayın, bu nedenle bu uzun şablon bağımsız değişkenleri satırını yazmanız gerekmez). Sonra, Index parametresi NULL değilse DB_E_NOINDEX döndürün (Bu, tüketicinin ABD 'de bir dizin kullanmasını istediğini gösterir). Komut kimlikleri hakkında daha fazla bilgi için OLE DB belirtimine bakın ve arama yapın `IOpenRowset::OpenRowset` .

Aşağıdaki kod `ValidateCommandID` doğrulama yordamdır:

```cpp
/////////////////////////////////////////////////////////////////////
// CustomRS.H
// Class: CCustomRowset

HRESULT ValidateCommandID(DBID* pTableID, DBID* pIndexID)
{
   HRESULT hr = _RowsetBaseClass::ValidateCommandID(pTableID, pIndexID);
   if (hr != S_OK)
      return hr;

   if (pIndexID != NULL)
      return DB_E_NOINDEX;    // Doesn't support indexes

   return S_OK;
}
```

Sağlayıcı şablonları, `OnPropertyChanged` kullanıcı dbpropset_rowset grubundaki bir özelliği her değiştirdiğinde yöntemini çağırır. Diğer grupların özelliklerini işlemek istiyorsanız, bunları uygun nesneye eklersiniz (yani DBPROPSET_SESSION denetimleri `CCustomSession` sınıfa gider).

Kod, özelliğin diğer ile bağlantılı olup olmadığını kontrol eder. Özellik zincirleme ise, DBPROP_BOOKMARKS özelliğini olarak ayarlar `True` . OLE DB belirtiminin ek C özellikleri hakkında bilgi içerir. Bu bilgiler ayrıca, özelliğin başka birine zincirlendiği konusunda da size bildirir.

Ayrıca, bu yordamı kodunuza eklemek isteyebilirsiniz `IsValidValue` . `IsValidValue`Bir özellik ayarlanmaya çalışılırken şablonlar çağrısı. Bir özellik değeri ayarlanırken ek işlem yapmanız gerekiyorsa, bu yöntemi geçersiz kılabilirsiniz. Her özellik kümesi için bu yöntemlerden birini kullanabilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[Gelişmiş sağlayıcı teknikleri](../../data/oledb/advanced-provider-techniques.md)
