|docker build| |docker pulls| |license| 

.. |docker build| image:: https://img.shields.io/docker/cloud/build/xridge/invex.svg
.. |docker pulls| image:: https://img.shields.io/docker/pulls/xridge/invex.svg
.. |license| image:: https://img.shields.io/badge/License-Apache%202.0-blue.svg

=====
invex
=====

Risk analytics application for `Interactive Brokers`_ `Flex Statements`_.
Capable of downloading and processing XML typed `Flex Statements`_ into
a report containing the key portfolio metrics:

  - Annual & Cumulative returns
  - Annual volatility
  - Sharpe, Calmar, Omega, Sortino & Tail Ratio
  - Alpha & Beta
  - Skew & Kurtosis
  - Max Drawdown & Daily Value at Risk
  
The flex statements are downloaded and transformed via Flexfolio_ to be
consumed by PyFolio_ and Empyrical_ packages.

.. _`Interactive Brokers`: https://www.interactivebrokers.com
.. _`Flex Statements`: https://www.interactivebrokers.com/en/software/am/am/reports/activityflexqueries.htm
.. _PyFolio: https://github.com/quantopian/pyfolio
.. _Empyrical: https://github.com/quantopian/empyrical
.. _Flexfolio: https://github.com/xridge/flexfolio

Usage
-----
.. code-block:: shell

  $ docker run -v $(pwd)/workdir:/workdir xridge/invex:latest fetch_statement IB_API_KEY QUERY_ID /workdir/flex_report.xml
  2019-04-24 22:23:17,097 - invex.cli - INFO - Requesting statement
  2019-04-24 22:23:17,770 - invex.cli - INFO - Downloading statement
  
  $ docker run -v $(pwd)/workdir:/workdir xridge/invex:latest to_pdf /workdir/flex_report.xml
  2019-04-24 22:29:30,951 - invex.pyfolio_wrapper - INFO - Report created: /workdir/flex_statement.pdf

License
-------
Copyright (c) 2019 `xridge.io`_

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

`Apache License Version 2.0`_

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.

.. _`xridge.io`: https://xridge.io
.. _`Apache License Version 2.0`: http://www.apache.org/licenses/LICENSE-2.0
