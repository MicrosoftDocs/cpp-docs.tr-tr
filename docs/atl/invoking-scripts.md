---
title: (ATL) betikleri çağırma
ms.date: 11/04/2016
helpviewer_keywords:
- StringRegister method
- scripts, invoking registry in ATL
ms.assetid: eabd41ee-586b-4266-9e92-5aaad04b73a4
ms.openlocfilehash: 6ca744ced53677550e7b77f44d4f6550da744372
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57820566"
---
# <a name="invoking-scripts"></a>Betikleri çağırma

[Değiştirilebilir parametreler (kaydedicinin ön işlemcisi) kullanarak](../atl/using-replaceable-parameters-the-registrar-s-preprocessor.md) değiştirme haritalar açıklanır ve kayıt şirketi yöntemi bahsetmeleri **AddReplacement**. Kayıt şirketi sekiz komut belirli bir yöntemi diğer sahiptir ve tüm aşağıdaki tabloda açıklanmıştır.

|Yöntem|Söz dizimi/açıklaması|
|------------|-------------------------|
|**ResourceRegister**|**HRESULT ResourceRegister (LPCOLESTR***resFileName* **, UINT** `nID` **, LPCOLESTR** `szType` **);**<br /><br /> Bir modülün kaynakta yer alan komut dosyası kaydeder. *resFileName* modülü UNC yolunu gösterir. *nID* ve *szType* kaynak kimliği ve türü içerir.|
|**ResourceUnregister**|**HRESULT ResourceUnregister (LPCOLESTR***resFileName* **, UINT** `nID` **, LPCOLESTR** `szType` **);**<br /><br /> Bir modülün kaynakta yer alan komut kaydını siler. *resFileName* modülü UNC yolunu gösterir. *nID* ve *szType* kaynak kimliği ve türü içerir.|
|**ResourceRegisterSz**|**HRESULT ResourceRegisterSz (LPCOLESTR***resFileName* **, LPCOLESTR***szID* **, LPCOLESTR** `szType` **);**<br /><br /> Bir modülün kaynakta yer alan komut dosyası kaydeder. *resFileName* modülü UNC yolunu gösterir. *szID* ve *szType* kaynağın dize tanımlayıcı ve türü içerir.|
|**ResourceUnregisterSz**|**HRESULT ResourceUnregisterSz (LPCOLESTR***resFileName* **, LPCOLESTR***szID* **, LPCOLESTR** `szType` **);**<br /><br /> Bir modülün kaynakta yer alan komut kaydını siler. *resFileName* modülü UNC yolunu gösterir. *szID* ve *szType* kaynağın dize tanımlayıcı ve türü içerir.|
|**FileRegister**|**HRESULT FileRegister( LPCOLESTR**  *fileName*  **);**<br /><br /> Betik bir dosyaya kaydeder. *fileName* kaynak betiği içeren (veya olan) bir dosya bir UNC yoludur.|
|**FileUnregister**|**HRESULT FileUnregister( LPCOLESTR**  *fileName*  **);**<br /><br /> Bir dosyadaki betik kaydını siler. *fileName* kaynak betiği içeren (veya olan) bir dosya bir UNC yoludur.|
|**StringRegister**|**HRESULT StringRegister (LPCOLESTR***veri***);**<br /><br /> Betik, bir dize kaydeder. *veri* betiği içerir.|
|**StringUnregister**|**HRESULT StringUnregister (LPCOLESTR***veri***);**<br /><br /> Bir dizedeki betik kaydını siler. *veri* betiği içerir.|

**ResourceRegisterSz** ve **ResourceUnregisterSz**, benzer **ResourceRegister** ve **ResourceUnregister**, ancak bir dize belirtmenizi sağlar tanımlayıcısı.

Yöntemleri **FileRegister** ve **FileUnregister** komut bir kaynak dosyasında istemiyorsanız veya kendi dosyasında betik istiyorsanız kullanışlıdır. Yöntemleri **StringRegister** ve **StringUnregister** dinamik olarak ayrılan bir dizede depolanacak .rgs dosya izin verin.

## <a name="see-also"></a>Ayrıca bkz.

[Kaydedici Betikleri Oluşturma](../atl/creating-registrar-scripts.md)
