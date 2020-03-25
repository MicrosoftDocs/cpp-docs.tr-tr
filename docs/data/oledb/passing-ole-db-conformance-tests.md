---
title: OLE DB Uygunluk Testlerini Geçme
ms.date: 11/04/2016
helpviewer_keywords:
- testing, OLE DB providers
- testing providers
- conformance testing
- conformance testing [OLE DB]
- OLE DB providers, testing
ms.assetid: d1a4f147-2edd-476c-b452-0e6a0ac09891
ms.openlocfilehash: eda4dccda147ddd4776bb56e649f539a7550abd1
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80209809"
---
# <a name="passing-ole-db-conformance-tests"></a>OLE DB Uygunluk Testlerini Geçme

Sağlayıcıları daha tutarlı hale getirmek için, veri erişim SDK 'Sı bir OLE DB uygunluk testi kümesi sağlar. Testler sağlayıcınızın tüm yönlerini denetler ve sağlayıcınızın beklendiği gibi işlev görür. OLE DB uyumluluk testlerini Microsoft veri erişimi SDK 'sında bulabilirsiniz. Bu bölüm, uyumluluk testlerini geçirmek için yapmanız gereken şeylere odaklanmaktadır. OLE DB uygunluk testlerini çalıştırma hakkında daha fazla bilgi için bkz. SDK.

## <a name="running-the-conformance-tests"></a>Uygunluk testlerini çalıştırma

Visual C++ 6,0 ' de OLE DB sağlayıcısı şablonları, değerleri ve özellikleri kontrol etmek için bir dizi ekleme işlevi eklemiştir. Bu işlevlerin çoğu, uygunluk testlerine yanıt olarak eklenmiştir.

> [!NOTE]
> Sağlayıcınızın OLE DB uygunluk testlerini geçirmesi için birkaç doğrulama işlevi eklemeniz gerekir.

Bu sağlayıcı iki doğrulama yordamı gerektirir. İlk yordam `CRowsetImpl::ValidateCommandID`, satır kümesi sınıfınızın bir parçasıdır. Sağlayıcı şablonları tarafından satır kümesi oluşturma sırasında çağrılır. Örnek, tüketicilere dizinleri desteklemediğini söylemek için bu yordamı kullanır. İlk çağrı `CRowsetImpl::ValidateCommandID`. (sağlayıcının, [yer işaretleri Için sağlayıcı desteğinin](../../data/oledb/provider-support-for-bookmarks.md)`CCustomRowset` için arabirim eşlemesinde eklenen `_RowsetBaseClass` typedef 'i kullandığını unutmayın. bu nedenle, bu uzun şablon bağımsız değişkenlerinin uzun satırını yazmanız gerekmez). Sonra, Index parametresi NULL değilse DB_E_NOINDEX döndürün (Bu, tüketicinin ABD 'de bir dizin kullanmasını istediğini gösterir). Komut kimlikleri hakkında daha fazla bilgi için OLE DB belirtimine bakın ve `IOpenRowset::OpenRowset`bakın.

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

Sağlayıcı şablonları, birisi DBPROPSET_ROWSET grubundaki bir özelliği her değiştirdiğinde `OnPropertyChanged` yöntemini çağırır. Diğer grupların özelliklerini işlemek istiyorsanız, bunları uygun nesneye eklersiniz (yani DBPROPSET_SESSION denetimleri `CCustomSession` sınıfında olur).

Kod, özelliğin diğer ile bağlantılı olup olmadığını kontrol eder. Özellik zincirleme ise, DBPROP_BOOKMARKS özelliğini `True`olarak ayarlar. OLE DB belirtiminin ek C özellikleri hakkında bilgi içerir. Bu bilgiler ayrıca, özelliğin başka birine zincirlendiği konusunda da size bildirir.

Ayrıca `IsValidValue` yordamını kodunuza eklemek isteyebilirsiniz. Şablonlar, bir özelliği ayarlamaya çalışırken `IsValidValue` çağırır. Bir özellik değeri ayarlanırken ek işlem yapmanız gerekiyorsa, bu yöntemi geçersiz kılabilirsiniz. Her özellik kümesi için bu yöntemlerden birini kullanabilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[Gelişmiş Sağlayıcı Teknikleri](../../data/oledb/advanced-provider-techniques.md)
