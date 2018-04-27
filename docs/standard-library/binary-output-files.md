---
title: İkili çıktı dosyaları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- I/O [C++], binary output files
- files [C++], binary output files
- binary data, binary output files
ms.assetid: 180954af-8cd6-444b-9a76-2f630a3389d8
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3456d410d0322f4843bc99b024ea0440ac1b93e8
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="binary-output-files"></a>İkili Çıktı Dosyaları

Varsayılan çıkış modu metindir şekilde akışları başlangıçta metin için tasarlanmıştır. Metin modunda yeni satır karakteri (onaltılık 10) bir satır başı-satır besleme için (yalnızca 16 bit) genişletir. Genişletme, aşağıda gösterildiği gibi sorunlara neden olabilir:

```cpp
// binary_output_files.cpp
// compile with: /EHsc
#include <fstream>
using namespace std;
int iarray[2] = { 99, 10 };
int main( )
{
    ofstream os( "test.dat" );
    os.write( (char *) iarray, sizeof( iarray ) );
}
```

{99, 0, 10, 0}; bayt dizisi çıkarmak için bu programı bekleyebilirsiniz Bunun yerine, onu {99, 0, 13, 10, 0}, ikili girişi bekleniyor bir program için sorunlara neden olan çıkarır. Untranslated karakter yazılır ikili çıktıyı true varsa, kullanarak ikili çıktıyı belirtebilirsiniz [ofstream](../standard-library/basic-ofstream-class.md#basic_ofstream) Oluşturucu AçmaModu bağımsız değişkeni:

```cpp
// binary_output_files2.cpp
// compile with: /EHsc
#include <fstream>
using namespace std;
int iarray[2] = { 99, 10 };

int main()
{
   ofstream ofs ( "test.dat", ios_base::binary );

   // Exactly 8 bytes written
   ofs.write( (char*)&iarray[0], sizeof(int)*2 );
}
```

## <a name="see-also"></a>Ayrıca bkz.

[Çıkış Akışları](../standard-library/output-streams.md)<br/>
