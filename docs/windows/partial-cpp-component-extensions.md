---
title: "Kısmi (C++ bileşen uzantıları) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: partial_CPP
dev_langs: C++
helpviewer_keywords:
- partial
- C++/CX, partial
ms.assetid: 43adf1f5-10c5-44aa-a66f-7507e2bdabf8
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: dd2debe47b0c60907c1a75f4e8b96d227468a345
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="partial--c-component-extensions"></a>kısmi (C++ Bileşen Uzantıları)
`partial` Anahtar sözcüğü bağımsız olarak ve farklı dosyaların yazılmasını aynı ref sınıfı farklı bölümlerini etkinleştirir.  
  
## <a name="all-runtimes"></a>Tüm Çalışma Zamanları  
 (Bu dil özellik yalnızca Windows çalışma zamanı için geçerlidir.)  
  
## <a name="windows-runtime"></a>Windows Çalışma Zamanı  
 İki kısmi tanımlarına sahip bir ref sınıf için `partial` anahtar sözcüğü tanımı ilk oluşumuna uygulanır ve İnsan Kodlayıcı anahtar sözcüğü çok sık kullanmaz, bu genellikle otomatik olarak oluşturulan kodu tarafından yapılır. İçin tüm sonraki kısmi tanımları sınıfının atlayın `partial` gelen değiştiricisi *sınıf anahtarı* anahtar sözcüğü ve sınıf tanımlayıcısı. Önceden tanımlanmış ref sınıfı ve sınıf tanımlayıcısı ancak hiçbir derleyici karşılaştığında `partial` anahtar sözcüğü, onu dahili olarak tüm ref sınıf tanımının bir tanım içine bölümlerini birleştirir.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
partial class-key identifier {  
   /* The first part of the partial class definition. 
      This is typically auto-generated */  
}  
// ...  
class-key identifier {  
   /* The subsequent part(s) of the class definition. The same 
      identifier is specified, but the "partial" keyword is omitted. */  
}  
```  
  
### <a name="parameters"></a>Parametreler  
 *sınıf anahtarı*  
 Bir sınıf ya da Windows çalışma zamanı tarafından desteklenen yapı bildiren bir anahtar sözcük. Her iki `ref class`, `value class`, `ref struct`, veya `value struct`.  
  
 *tanımlayıcı*  
 Tanımlı türünün adı.  
  
### <a name="remarks"></a>Açıklamalar  
 Kısmi bir sınıf bir dosya ve otomatik kod oluşturma yazılım sınıf tanımının bir parçası, değişiklik burada senaryolarını destekler — Örneğin, XAML Tasarımcısı — başka bir dosya aynı sınıfta kodda değiştirir. Kısmi bir sınıf kullanarak kodunuzu üzerine yazılmasını otomatik kod Oluşturucu engelleyebilir. Visual Studio Proje `partial` değiştiricisi oluşturulan dosya otomatik olarak uygulanır.  
  
 İçeriği: iki özel durum ile bir parçalı sınıf tanımı tam sınıf tanımını varsa içerebilecek herhangi bir şey içerebilir `partial` anahtar sözcüğü yoksayıldı. Ancak, sınıf erişilebilirlik belirtilemez (örneğin, `public partial class X { ... };`), veya bir `declspec`.  
  
 Erişim için bir parçalı sınıf tanımında kullanılan tanımlayıcıları *tanımlayıcısı* bir sonraki kısmi veya tam sınıf tanımında varsayılan erişilebilirlik etkilemez *tanımlayıcısı*. Satır içi tanımları statik veri üyeleri izin verilir.  
  
 Bildirimi: Bir kısmi bir sınıfın tanımını *tanımlayıcısı* yalnızca adı tanıtır *tanımlayıcısı*, ancak *tanımlayıcısı* bir sınıf gerektiren bir şekilde kullanılamaz tanımı. Adı *tanımlayıcısı* boyutunu bilmek kullanılamaz *tanımlayıcısı*, veya bir temel veya üyesi kullanmak için *tanımlayıcısı* kadar tam tanımı derleyici karşılaştığında sonra *tanımlayıcısı*.  
  
 Sayı ve sıralama: sıfır veya daha çok parçalı sınıf tanımlarını olabilir *tanımlayıcısı*. Her parçalı sınıf tanımını *tanımlayıcısı* sözcüksel olarak bir tam tanımı gelmelidir *tanımlayıcısı* (varsa tam tanımı; Aksi takdirde sınıfı dışında kullanılamaz olur İleri-bildirilen) ancak, iletme bildirimlerden önce olmayan *tanımlayıcısı*. Tüm sınıf anahtarlarının eşleşmesi gerekir.  
  
 Tam tanımı: sınıfının tam tanımını noktasında *tanımlayıcısı*, aynı davranıştır gibi tanımını *tanımlayıcısı* bildirilen tüm temel sınıflar, üyeler, vb. hangi sırayla Bunlar karşılaştı ve kısmi sınıflarda tanımlanan.  
  
 Şablonlar: Bir şablon bir parçalı sınıf olamaz.  
  
 Genel türler: tam tanımı genel bir parçalı sınıf genel olabilir. Ancak her kısmi ve tam sınıfı biçimsel parametresi adları dahil olmak üzere tam olarak aynı genel parametreleri, olması gerekir.  
  
 Nasıl kullanılacağı hakkında daha fazla bilgi için `partial` anahtar sözcüğü, bkz: [kısmi sınıflar (C + +/ CX)](http://go.microsoft.com/fwlink/p/?LinkId=249023).  
  
### <a name="requirements"></a>Gereksinimler  
 Derleyici seçeneği: **/ZW**  
  
## <a name="common-language-runtime"></a>Ortak Dil Çalışma Zamanı  
 (Bu dil özelliği ortak dil çalışma zamanı için uygulanmaz.)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kısmi sınıflar (C + +/ CX)](http://go.microsoft.com/fwlink/p/?LinkId=249023)