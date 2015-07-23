%Matlab
%Matlab .m files
%% function repnan
function [varargout]=repnan(r,varargin)
%REPNAN  Replace NaN values by arbitrary number
%========================================================================
%r: NaN is replaced by r
%varargin: any number of arrays with any input dimentions is accepted
%varagout: number of output arrays has to be equal to input arrays
%copyright@2015 Dr. Roohollah Kalatehjari
%free to use in any project with reference to above mentioned copyrigth
%========================================================================
narginchk(1,nargin);    %error: Not enough input arguments.
nout = max(nargout,1); 	%number of output variables
if nout~=size(varargin,2);error('imbalance input and output');end
for i=1:nout %size(varargin,2)
    matin=cell2mat(varargin(i));
    matin(isnan(matin))=r;
    matout(i)={matin};
end
varargout=matout;
%========================================================================
end
