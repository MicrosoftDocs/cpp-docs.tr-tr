---
title: Derleyici Uyarısı (Düzey 2) C4275 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4275
dev_langs:
- C++
helpviewer_keywords:
- C4275
ms.assetid: 18de967a-0a44-4dbc-a2e8-fc4c067ba909
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a5d2a3cd7c4b937f8bee1b8f8e37e0619cc224ba
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-2-c4275"></a>Derleyici Uyarısı (Düzey 2) C4275
olmayan - DLL arabirim classkey 'tanımlayıcısı' temel olarak kullanılan DLL arabirimi classkey 'tanımlayıcısı'  
  
 Dışarı aktarılan bir sınıf verilemedi sınıfından türetilmiş.  
  
 Bir sınıfla verilirken veri bozulması olasılığını en aza indirmek için [__declspec(dllexport)](../../cpp/dllexport-dllimport.md), emin olun:  
  
-   Tüm statik verilerinizi DLL'den dışarı aktarılan işlevler aracılığıyla erişilir.  
  
-   Sınıfınızın içermesinden hiçbir yöntemi statik verileri değiştirebilirsiniz.  
  
-   Hiçbir satır içi yöntemi sınıfınızın CRT işlevleri veya diğer kitaplık işlevleri statik verileri kullanın.  
  
-   Hiçbir satır içi sınıfı işlevleri, burada, örneğin, statik verilere CRT işlevleri veya diğer kitaplık işlevleri kullanın.  
  
-   Hiçbir yöntemi sınıfınızın (bağımsız olarak, satır içi kullanım) örnekleme EXE ve DLL içinde statik verileri farklılıkları olduğu türlerini kullanabilirsiniz.  
  
 Sanal işlevlere sahip bir sınıf tanımlar ve işlevleri DLL örneği oluşturmak için çağırabilirsiniz tanımlama ve delete Nesne türü tarafından sınıfları dışarı aktarma önleyebilirsiniz.  Ardından yalnızca sanal işlevler türüne çağırabilirsiniz.  
  
 Şablonları dışarı aktarma ile ilgili daha fazla bilgi için bkz: [ http://support.microsoft.com/default.aspx?scid=KB; EN-US; 168958](http://support.microsoft.com/default.aspx?scid=KB;EN-US;168958).  
  
 C4275 dikkate Visual C++'da bir tür kitaplığı'nda C++ standart bir hata ayıklama yayın derleme türetme varsa (**/MTd**) ve derleyici hata iletisi için _Container_base olduğu anlamına gelir.  
  
```  
// C4275.cpp  
// compile with: /EHsc /MTd /W2 /c  
#include <vector>  
using namespace std;  
class Node;  
class __declspec(dllimport) VecWrapper : vector<Node *> {};   // C4275  
```