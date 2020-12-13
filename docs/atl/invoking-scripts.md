---
description: 'Daha fazla bilgi edinin: betikleri çağırma'
title: Betikleri çağırma (ATL)
ms.date: 11/04/2016
helpviewer_keywords:
- StringRegister method
- scripts, invoking registry in ATL
ms.assetid: eabd41ee-586b-4266-9e92-5aaad04b73a4
ms.openlocfilehash: 48fc49118d93893b5cd60462fbaecfdb73d747c3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97152665"
---
# <a name="invoking-scripts"></a>Betikleri çağırma

[Değiştirilebilir parametrelerin kullanılması (kaydedici 'nin ön işlemcisi)](../atl/using-replaceable-parameters-the-registrar-s-preprocessor.md) , değişiklik haritalarını açıklar ve kayıt yöntemi **adddeğiştirme** yöntemi ile bahseder. Kayıt kaydedicisinde, komut dosyası oluşturmaya özgü sekiz farklı yöntem vardır ve bunların tümü aşağıdaki tabloda açıklanmıştır.

|Yöntem|Söz dizimi/açıklama|
|------------|-------------------------|
|**ResourceRegister**|**HRESULT ResourceRegister (lpcolistr***resFileName* **, UINT** `nID` **, lpcotastr** `szType` **);**      <br /><br /> Modülün kaynağında bulunan betiği kaydeder. *resFileName* modülün kendısı için UNC yolunu gösterir. *NID* ve *sztype* , sırasıyla kaynağın kimliğini ve türünü içerir.|
|**ResourceUnregister**|**HRESULT ResourceUnregister (lpcolistr***resFileName* **, UINT** `nID` **, lpcotastr** `szType` **);**      <br /><br /> Modülün kaynağında bulunan betiğin kaydını siler. *resFileName* modülün kendısı için UNC yolunu gösterir. *NID* ve *sztype* , sırasıyla kaynağın kimliğini ve türünü içerir.|
|**ResourceRegisterSz**|**HRESULT ResourceRegisterSz (lpcolonstr***resFileName* **, lpcolistr***szID* **, lpcolistr** `szType` **);**      <br /><br /> Modülün kaynağında bulunan betiği kaydeder. *resFileName* modülün kendısı için UNC yolunu gösterir. *szID* ve *sztype* , sırasıyla kaynağın dize tanımlayıcısını ve türünü içerir.|
|**ResourceUnregisterSz**|**HRESULT ResourceUnregisterSz (lpcolonstr***resFileName* **, lpcolistr***szID* **, lpcolistr** `szType` **);**      <br /><br /> Modülün kaynağında bulunan betiğin kaydını siler. *resFileName* modülün kendısı için UNC yolunu gösterir. *szID* ve *sztype* , sırasıyla kaynağın dize tanımlayıcısını ve türünü içerir.|
|**FileRegister**|**HRESULT Dosyasıyumurtayı (LPCOPASTR**  *filename*  **);**<br /><br /> Betiği bir dosyaya kaydeder. *filename* , bir kaynak betiği içeren (veya olan) BIR dosyanın UNC yoludur.|
|**FileUnregister**|**HRESULT FileUnregister (LPCOLISTR**  *filename*  **);**<br /><br /> Dosyadaki betiğin kaydını siler. *filename* , bir kaynak betiği içeren (veya olan) BIR dosyanın UNC yoludur.|
|**StringRegister**|**HRESULT StringRegister (LPCOLISTR**  *verileri*  **);**<br /><br /> Betiği bir dizeye kaydeder. *veri* , betiğin kendisini içerir.|
|**StringUnregister**|**HRESULT StringUnregister (LPCOLISTR**  *verileri*  **);**<br /><br /> Bir dizedeki betiğin kaydını siler. *veri* , betiğin kendisini içerir.|

**ResourceRegisterSz** ve **ResourceUnregisterSz**, **ResourceRegister** ve **ResourceUnregister** ile benzerdir, ancak bir dize tanımlayıcısı belirtmenize izin verir.

Bir kaynakta betiğin istemediğiniz veya komut dosyasının kendi dosyasında olmasını istemediğiniz durumlarda, **Fileregle** ve **FileUnregister** yöntemleri yararlıdır. **StringRegister** ve **StringUnregister** yöntemleri. rgs dosyasının dinamik olarak ayrılmış bir dizede depolanmasını sağlar.

## <a name="see-also"></a>Ayrıca bkz.

[Kaydedici betikleri oluşturma](../atl/creating-registrar-scripts.md)
