/*hover-opacity*/

.opacity-hover a {
  display: block;
  position: relative;
}
.opacity-hover a:before {
  background-color: #000;
  content: "";
  height: 100%;
  left: 0;
  opacity: 0;
  position: absolute;
  top: 0;
  transition: all 0.3s ease 0s;
  visibility: hidden;
  width: 100%;
}

.opacity-hover a:hover::before {
  opacity: 0.1;
  visibility: visible;
}
----------------------