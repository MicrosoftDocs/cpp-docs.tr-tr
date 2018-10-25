---
title: OLE DB uygunluk testlerini geçirme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- testing, OLE DB providers
- testing providers
- conformance testing
- conformance testing [OLE DB]
- OLE DB providers, testing
ms.assetid: d1a4f147-2edd-476c-b452-0e6a0ac09891
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 2be281252bc9166473eeb5d0e57a509941ad3673
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50057809"
---
# <a name="passing-ole-db-conformance-tests"></a>OLE DB Uygunluk Testlerini Geçme

Sağlayıcıları daha tutarlı hale getirmek için veri erişim SDK'sı bir OLE DB uygunluk testlerini sunmaktadır. Testleri sağlayıcınız tüm yönlerini denetleme ve sağlayıcı beklendiği gibi makul güvence verir. OLE DB uygunluk testlerini Microsoft Data Access SDK üzerinde bulabilirsiniz. Bu bölüm, uygunluk testleri geçirmek için yapmanız gerekenler üzerinde odaklanır. OLE DB uygunluk testlerini çalıştırma hakkında daha fazla bilgi için bkz.

## <a name="running-the-conformance-tests"></a>Uygunluk testlerini çalıştırma

Visual C++ 6.0, çok sayıda takma işlev değerleri ve özellikleri denetlemenizi izin vermek için OLE DB sağlayıcı şablonları eklendi. Bu işlevlerin çoğunu yanıt uygunluk testlerini olarak eklendi.

> [!NOTE]
> OLE DB uygunluk testlerini geçirilecek sağlayıcınız için çeşitli doğrulama işlevler eklemenize gerek.

Bu sağlayıcı iki doğrulama rutinleri gerektirir. İlk yordam `CRowsetImpl::ValidateCommandID`, satır kümesi sınıfının bir parçasıdır. Bu satır kümesi oluşturma sırasında sağlayıcı şablonları tarafından çağırılır. Örnek, tüketicilerin dizinlerini desteklemiyor bildirmek için bu yordamı kullanır. İlk çağrı `CRowsetImpl::ValidateCommandID` (sağlayıcısı kullanan Not `_RowsetBaseClass` ilişkin arabirim eşlemesini eklenen typedef `CCustomRowset` içinde [yer işaretleri sağlayıcı desteği](../../data/oledb/provider-support-for-bookmarks.md), uzun bir satır şablon türüne sahip değilsiniz bağımsız değişkenler). Ardından, dizin parametresi NULL değilse DB_E_NOINDEX döndürür. (Bu dizin bizi kullanmak isteyen tüketici gösterir). Komut kimlikleri hakkında daha fazla bilgi için OLE DB belirtimine bakın ve Ara `IOpenRowset::OpenRowset`.

Aşağıdaki kod `ValidateCommandID` doğrulama yordamına:

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

Sağlayıcı şablonları çağrı `OnPropertyChanged` her biri bir özellik değiştiğinde yöntemi `DBPROPSET_ROWSET` grubu. Diğer grupların özellikleri işlemek isterseniz, bunları uygun nesnesine eklediğiniz (diğer bir deyişle, `DBPROPSET_SESSION` denetimleri `CCustomSession` sınıfı).

Kod, ilk önce özelliğin diğerine bağlı olup olmadığını görmek için denetler. Özellik zincirlendiğini değilse, ayarlar `DBPROP_BOOKMARKS` özelliğini `True`. OLE DB belirtiminin ek C özellikleri hakkında bilgi içerir. Bu bilgileri ayrıca, özellik için başka bir zincir olup olmadığını bildirir.

Eklemek isteyebilirsiniz `IsValidValue` kodunuzda rutin. Şablonları çağrı `IsValidValue` bir özelliğini ayarlamaya çalışırken. Bir özellik değerini ayarlarken ek işleme gerekiyorsa bu yöntemi geçersiz kılarsınız. Her bir özellik kümesi için aşağıdaki yöntemlerden birini olabilir.

## <a name="see-also"></a>Ayrıca Bkz.

[Gelişmiş Sağlayıcı Teknikleri](../../data/oledb/advanced-provider-techniques.md)